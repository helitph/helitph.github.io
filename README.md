<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EitenoHub - Sites Profissionais em 2 Dias</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #0c0c0c, #1a1a1a);
            color: #ffffff;
            line-height: 1.7;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header ÉPICO */
        .header {
            text-align: center;
            padding: 100px 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 25px;
            margin-bottom: 60px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('https://images.unsplash.com/photo-1555066931-4365d14bab8c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80') center/cover;
            opacity: 0.15;
        }

        .header-content {
            position: relative;
            z-index: 2;
        }

        .header h1 {
            font-size: 4em;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ffffff, #f1c40f);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 800;
            text-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        .header p {
            font-size: 1.4em;
            opacity: 0.95;
            margin-bottom: 40px;
            font-weight: 300;
        }

        .badges {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
            flex-wrap: wrap;
        }

        .badge {
            background: rgba(255,255,255,0.25);
            padding: 12px 25px;
            border-radius: 50px;
            font-size: 1em;
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255,255,255,0.3);
            font-weight: 600;
        }

        /* Planos ULTRA PREMIUM */
        .planos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin: 80px 0;
        }

        .plano-card {
            background: linear-gradient(145deg, rgba(255,255,255,0.1), rgba(255,255,255,0.05));
            padding: 50px 35px;
            border-radius: 25px;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.15);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            backdrop-filter: blur(20px);
            position: relative;
            overflow: hidden;
        }

        .plano-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 6px;
            background: linear-gradient(90deg, #667eea, #764ba2, #f1c40f);
        }

        .plano-card:hover {
            transform: translateY(-20px) scale(1.02);
            border-color: #667eea;
            box-shadow: 0 25px 50px rgba(0,0,0,0.4);
        }

        .plano-card.destaque {
            border-color: #f1c40f;
            transform: scale(1.08);
            background: linear-gradient(145deg, rgba(241,196,15,0.15), rgba(255,255,255,0.1));
        }

        .plano-card.destaque::before {
            background: linear-gradient(90deg, #f1c40f, #e74c3c, #ff6b6b);
        }

        .plano-card.destaque:hover {
            transform: scale(1.1) translateY(-15px);
        }

        .plano-titulo {
            font-size: 1.8em;
            margin-bottom: 25px;
            color: #f1c40f;
            font-weight: 700;
        }

        .plano-preco {
            font-size: 3.5em;
            font-weight: 800;
            margin-bottom: 35px;
            color: #ffffff;
            text-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        .plano-preco span {
            font-size: 0.35em;
            color: #cccccc;
            display: block;
            margin-top: 8px;
            font-weight: 400;
        }

        .plano-lista {
            list-style: none;
            margin-bottom: 40px;
            text-align: left;
        }

        .plano-lista li {
            padding: 15px 0;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            position: relative;
            padding-left: 40px;
            font-size: 1.05em;
        }

        .plano-lista li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #27ae60;
            font-weight: bold;
            font-size: 1.3em;
        }

        .plano-lista li.negativo::before {
            content: '✗';
            color: #e74c3c;
        }

        .btn-comprar {
            display: inline-block;
            background: linear-gradient(135deg, #25D366, #128C7E);
            color: white;
            padding: 20px 40px;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1.2em;
            transition: all 0.3s ease;
            width: 100%;
            border: none;
            cursor: pointer;
            text-shadow: 0 1px 2px rgba(0,0,0,0.3);
            box-shadow: 0 5px 15px rgba(37, 211, 102, 0.3);
        }

        .btn-comprar:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(37, 211, 102, 0.5);
            background: linear-gradient(135deg, #128C7E, #25D366);
        }

        /* Garantias PREMIUM */
        .garantias {
            background: linear-gradient(135deg, rgba(255,255,255,0.08), rgba(255,255,255,0.03));
            padding: 70px 50px;
            border-radius: 25px;
            margin: 80px 0;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .garantias h2 {
            color: #f1c40f;
            margin-bottom: 50px;
            font-size: 2.8em;
            font-weight: 700;
        }

        .garantias-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 40px;
        }

        .garantia-item {
            padding: 40px 30px;
            background: rgba(255,255,255,0.08);
            border-radius: 20px;
            transition: transform 0.3s ease;
        }

        .garantia-item:hover {
            transform: translateY(-10px);
        }

        .garantia-icon {
            font-size: 4em;
            margin-bottom: 25px;
        }

        .garantia-item h3 {
            color: #f1c40f;
            margin-bottom: 15px;
            font-size: 1.4em;
        }

        .garantia-item p {
            color: #cccccc;
            line-height: 1.6;
        }

        /* Processo */
        .processo {
            margin: 80px 0;
        }

        .processo h2 {
            text-align: center;
            margin-bottom: 50px;
            color: #f1c40f;
            font-size: 2.5em;
        }

        .passos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .passo {
            background: rgba(255,255,255,0.08);
            padding: 40px 25px;
            border-radius: 15px;
            text-align: center;
            position: relative;
        }

        .passo-numero {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-weight: bold;
            font-size: 1.4em;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .contrato-destaque {
            background: rgba(241, 196, 15, 0.1);
            border: 2px solid #f1c40f;
            padding: 25px;
            border-radius: 15px;
            margin-top: 20px;
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 50px 20px;
            color: #888888;
            border-top: 1px solid rgba(255,255,255,0.1);
            margin-top: 80px;
            font-size: 1.1em;
        }

        /* Responsivo MELHORADO */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.8em;
            }
            
            .header p {
                font-size: 1.2em;
            }
            
            .planos {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            .plano-card.destaque {
                transform: none;
            }
            
            .plano-card:hover {
                transform: translateY(-10px);
            }
            
            .badges {
                gap: 10px;
            }
            
            .badge {
                padding: 10px 20px;
                font-size: 0.9em;
            }
        }

        @media (max-width: 480px) {
            .header {
                padding: 60px 20px;
            }
            
            .header h1 {
                font-size: 2.2em;
            }
            
            .plano-card {
                padding: 35px 25px;
            }
            
            .plano-preco {
                font-size: 2.8em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header ÉPICO -->
        <header class="header">
            <div class="header-content">
                <h1>EitenoHub</h1>
                <p>Sites Profissionais que Impulsionam seu Negócio</p>
                <div class="badges">
                    <div class="badge">🚀 Entrega em 2 Dias</div>
                    <div class="badge">✅ Contrato Assinado</div>
                    <div class="badge">💳 Pagamento Seguro</div>
                    <div class="badge">🛡️ Garantia Total</div>
                </div>
            </div>
        </header>

        <!-- Planos ULTRA PREMIUM -->
        <section class="planos">
            <!-- Plano Básico -->
            <div class="plano-card">
                <div class="plano-titulo">💼 Site Básico</div>
                <div class="plano-preco">R$ 80<span>Pagamento único</span></div>
                <ul class="plano-lista">
                    <li>1 página principal responsiva</li>
                    <li>Design moderno e profissional</li>
                    <li>Formulário de contato integrado</li>
                    <li>Botão WhatsApp direto</li>
                    <li>Otimização básica SEO</li>
                    <li>Entrega em 2 dias úteis</li>
                    <li class="negativo">Sem atualizações futuras</li>
                </ul>
                <a href="https://wa.me/5511958490459?text=💼 Olá! Quero o Site BÁSICO de R$80" class="btn-comprar" target="_blank">
                    💰 Quero este Plano
                </a>
            </div>

            <!-- Plano Intermediário -->
            <div class="plano-card destaque">
                <div class="plano-titulo">🚀 Site Completo</div>
                <div class="plano-preco">R$ 120<span>Pagamento único</span></div>
                <ul class="plano-lista">
                    <li>Até 5 páginas personalizadas</li>
                    <li>Design exclusivo e moderno</li>
                    <li>Galeria de fotos integrada</li>
                    <li>Mapa de localização</li>
                    <li>SEO otimizado para Google</li>
                    <li>Integração com redes sociais</li>
                    <li>Suporte por 7 dias</li>
                    <li>Entrega em 2 dias úteis</li>
                </ul>
                <a href="https://wa.me/5511958490459?text=🚀 Olá! Quero o Site COMPLETO de R$120" class="btn-comprar" target="_blank">
                    🎯 Plano Mais Vendido
                </a>
            </div>

            <!-- Plano Profissional -->
            <div class="plano-card">
                <div class="plano-titulo">💎 Site Profissional</div>
                <div class="plano-preco">R$ 150<span>Pagamento único</span></div>
                <ul class="plano-lista">
                    <li>Páginas ilimitadas</li>
                    <li>Design premium exclusivo</li>
                    <li>Sistema de agendamento</li>
                    <li>Blog integrado</li>
                    <li>SEO avançado</li>
                    <li>Google Analytics</li>
                    <li>Otimização máxima</li>
                    <li>Suporte por 30 dias</li>
                    <li>Entrega em 2 dias úteis</li>
                </ul>
                <a href="https://wa.me/5511958490459?text=💎 Olá! Quero o Site PROFISSIONAL de R$150" class="btn-comprar" target="_blank">
                    ⚡ Plano Premium
                </a>
            </div>
        </section>

        <!-- Garantias PREMIUM -->
        <section class="garantias">
            <h2>🛡️ Segurança Total para Você</h2>
            <div class="garantias-grid">
                <div class="garantia-item">
                    <div class="garantia-icon">📝</div>
                    <h3>Contrato Assinado</h3>
                    <p>Acordo formal com todas as cláusulas de proteção para ambas as partes</p>
                </div>
                <div class="garantia-item">
                    <div class="garantia-icon">💳</div>
                    <h3>Pagamento Seguro</h3>
                    <p>50% na assinatura do contrato e 50% na entrega do projeto</p>
                </div>
                <div class="garantia-item">
                    <div class="garantia-icon">⚖️</div>
                    <h3>Garantia Legal</h3>
                    <p>Seu investimento protegido por contrato válido juridicamente</p>
                </div>
                <div class="garantia-item">
                    <div class="garantia-icon">🚀</div>
                    <h3>Entrega Garantida</h3>
                    <p>Site no ar em 2 dias úteis ou devolução do sinal</p>
                </div>
            </div>
        </section>

        <!-- Processo com Contrato -->
        <section class="processo">
            <h2>📋 Como Funciona com Contrato</h2>
            <div class="passos">
                <div class="passo">
                    <div class="passo-numero">1</div>
                    <h3>Escolha do Plano</h3>
                    <p>Você seleciona o plano ideal para seu negócio</p>
                    <div class="contrato-destaque">
                        <strong>CONTRATO:</strong> Definição dos escopos e valores
                    </div>
                </div>
                <div class="passo">
                    <div class="passo-numero">2</div>
                    <h3>Assinatura & Pagamento</h3>
                    <p>Enviamos contrato e você paga 50% de entrada</p>
                    <div class="contrato-destaque">
                        <strong>CONTRATO:</strong> Assinatura digital + Pagamento seguro
                    </div>
                </div>
                <div class="passo">
                    <div class="passo-numero">3</div>
                    <h3>Desenvolvimento</h3>
                    <p>Criamos seu site em 2 dias úteis</p>
                    <div class="contrato-destaque">
                        <strong>CONTRATO:</strong> Prazo garantido por escrito
                    </div>
                </div>
                <div class="passo">
                    <div class="passo-numero">4</div>
                    <h3>Entrega & Aprovação</h3>
                    <p>Você aprova e paga os 50% restantes</p>
                    <div class="contrato-destaque">
                        <strong>CONTRATO:</strong> Liberação final após aprovação
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <p>© 2024 EitenoHub - Desenvolvimento de Sites Profissionais</p>
            <p style="margin-top: 15px; font-size: 1em; color: #f1c40f;">
                📞 WhatsApp: (11) 95849-0459 | 📝 Contrato assinado | 🚀 Entrega em 2 dias
            </p>
        </footer>
    </div>

    <script>
        // Efeito de digitação no título
        document.addEventListener('DOMContentLoaded', function() {
            const cards = document.querySelectorAll('.plano-card');
            cards.forEach((card, index) => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(50px)';
                
                setTimeout(() => {
                    card.style.transition = 'all 0.8s ease';
                    card.style.opacity = '1';
                    card.style.transform = 'translateY(0)';
                }, index * 300);
            });
        });
    </script>
</body>
</html>
