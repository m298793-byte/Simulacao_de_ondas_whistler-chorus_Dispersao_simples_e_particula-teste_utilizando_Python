Simulação de Ondas Whistler/Chorus
Dispersão a Frio e Partícula-Teste com Python

Autores:

Mauricio Alejandro González Lucero Villalba

Gustavo Schulte

Luis Monteiro

Orientador:

Gustavo do Amaral Valdiviesso

  Descrição Geral

Este repositório apresenta uma simulação didática de ondas whistler/chorus na magnetosfera terrestre. O projeto contém duas partes principais:

Cálculo da dispersão fria do modo R (whistler), gerando o gráfico k(omega).

Simulação de uma partícula-teste (elétron) movendo-se em um campo magnético uniforme (B0) e um campo elétrico oscilante que representa a onda.

O objetivo é conectar física de plasmas com técnicas de programação científica em Python, como integração numérica, FFT, varreduras em parâmetros e visualização de resultados.

  Contexto Físico

Na magnetosfera, elétrons giram em torno das linhas do campo magnético com uma frequência natural chamada frequência ciclotrônica, dada por:

Omega_e = e * B0 / m_e

Quando a frequência da onda whistler se aproxima desta frequência natural, ocorre a ressonância ciclotrônica.
Nesta condição a onda transfere energia continuamente para o elétron, modificando sua órbita e aumentando sua energia cinética.

O projeto permite visualizar:

regiões onde a onda pode se propagar (n^2 >= 0);

órbitas helicoidais com e sem onda;

ganho de energia K_final em função da frequência da onda;

robustez da ressonância ao variar a fase inicial da onda.

  Modelagem Matemática
Dispersão fria do modo R

Equação usada (sem derivação):

n^2(omega) = 1 - omega_pe^2 / [omega * (omega - Omega_e)]
k(omega) = n(omega) * omega / c

Somente pontos com n^2 >= 0 são incluídos no gráfico.

Movimento da partícula-teste

Equações resolvidas numericamente:

dx/dt = vx
dy/dt = vy
m * dv/dt = q * (E + v x B0)

Campo magnético uniforme:
B0 = (0, 0, B0)

Campo elétrico da onda:

E = (E0 * cos(k * x - omega * t + phi0), 0, 0)

A integração é feita com método Runge–Kutta de 4ª ordem (RK4), com passo dt pequeno o suficiente para estabilidade.

  Objetivos

Implementar dispersão fria do modo whistler.

Integrar a dinâmica da partícula em campos prescritos.

Observar a ressonância ciclotrônica.

Fazer varreduras em frequência e fase (Monte Carlo simples).

Gerar gráficos claros e reprodutíveis.

Aplicar FFT para análise espectral da onda.

Implementar uma versão reduzida de Vlasov (mini-Vlasov) usando partículas.

  Estrutura do Repositório
Projeto_Computacao_Cientifica.ipynb   # Notebook principal
config.json (opcional)                # Parâmetros externos
animations/                           # MP4 das animações
README.md                             # Este documento
LICENSE                               # Licença MIT

  Como Executar
Instalar dependências:

pip install numpy matplotlib

Abrir o notebook:

Google Colab (recomendado)

ou Jupyter Notebook local

Executar as seções:

Cálculo da dispersão k(omega)

Partícula-teste

Varredura de frequências

FFT

Heatmap K_final(omega, fase)

Mini-Vlasov

Animações

Cada célula está comentada e organizada.

  Resultados Obtidos

Gráfico de dispersão k(omega) mostrando regiões permitidas e proibidas.

Órbita helicoidal do elétron com modificação causada pela onda.

Pico de energia K_final na frequência de ressonância.

Heatmap mostrando robustez da ressonância.

Espectro obtido via FFT.

Evolução de uma nuvem de partículas (mini-Vlasov).

  Arquitetura Computacional

Integrador RK4 estável.

Máscara para descartar pontos com n^2 < 0.

Varreduras otimizadas em frequência e fase.

Testes de convergência (redução de dt).

Verificação de conservação de energia quando E0 = 0.

Exportação de animações para MP4.

Uso de sementes para reprodutibilidade numérica.

  Conclusões

O projeto demonstra de forma clara o mecanismo de ressonância ciclotrônica e sua importância na física de plasmas e na geração de ondas chorus.
Além disso, desenvolve habilidades práticas em modelagem física, programação científica, simulação numérica e análise gráfica.

  Referências

As referências completas estão no arquivo bibliografia.tex no Overleaf:

Stix (1992) — Waves in Plasmas

Omura et al. (2008) — Generation of whistler-mode chorus

Helliwell (1965) — Whistlers and related phenomena

Chen (2016) — Introduction to Plasma Physics

Hunter (2007) — Matplotlib

📜 Licença

Este projeto está sob a MIT License.
Uso livre com atribuição aos autores.
