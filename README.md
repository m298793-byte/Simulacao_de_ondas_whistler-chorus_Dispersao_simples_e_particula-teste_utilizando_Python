Simulação de Ondas Whistler/Chorus
Dispersão a Frio e Partícula-Teste com Python

Autores:

Mauricio Alejandro González Lucero Villalba

Gustavo Schulte

Luis Monteiro

Orientador:

Gustavo do Amaral Valdiviesso

Descrição Geral

Este repositório apresenta uma simulação didática de ondas whistler/chorus na magnetosfera terrestre. O projeto contempla:

Dispersão fria do modo R (whistler), obtendo a relação 
𝑘
(
𝜔
)
k(ω).

Partícula-teste, simulando o movimento de um elétron sob a ação de um campo magnético uniforme 
𝐵
0
B
0
	​

 e um campo elétrico oscilante representando a onda.

O trabalho reforça conceitos de física de plasmas, ressonância ciclotrônica, integração numérica e visualização científica usando Python (NumPy, Matplotlib, FFT e RK4).

Contexto Físico

Na magnetosfera terrestre, elétrons aprisionados executam movimento helicoidal em torno das linhas de campo magnético com frequência ciclotrônica:

Ω
𝑒
=
𝑒
𝐵
0
𝑚
𝑒
.
Ω
e
	​

=
m
e
	​

eB
0
	​

	​

.

Quando a frequência da onda whistler se aproxima deste valor, ocorre ressonância ciclotrônica, permitindo transferência contínua de energia da onda para o elétron.

A simulação permite observar:

regiões propagantes onde 
𝑛
2
(
𝜔
)
≥
0
n
2
(ω)≥0;

órbitas da partícula com e sem onda;

ganho de energia final 
𝐾
𝑓
(
𝜔
)
K
f
	​

(ω) mostrando um pico claro na ressonância;

robustez da ressonância ao variar a fase inicial 
𝜙
0
ϕ
0
	​

.

Modelagem Matemática
Dispersão fria (modo R)
𝑛
2
(
𝜔
)
=
1
−
𝜔
𝑝
𝑒
2
𝜔
(
𝜔
−
Ω
𝑒
)
,
𝑘
(
𝜔
)
=
𝑛
(
𝜔
)
 
𝜔
𝑐
.
n
2
(ω)=1−
ω(ω−Ω
e
	​

)
ω
pe
2
	​

	​

,k(ω)=
c
n(ω)ω
	​

.
Movimento da partícula-teste
𝑥
˙
=
𝑣
𝑥
,
𝑦
˙
=
𝑣
𝑦
,
x
˙
=v
x
	​

,
y
˙
	​

=v
y
	​

,
𝑚
 
𝑣
˙
=
𝑞
(
𝐸
+
𝑣
×
𝐵
0
)
,
m
v
˙
=q(E+v×B
0
	​

),

com:

𝐵
0
=
𝐵
0
 
𝑧
^
,
𝐸
=
𝐸
0
cos
⁡
(
𝑘
𝑥
−
𝜔
𝑡
+
𝜙
0
)
 
𝑥
^
.
B
0
	​

=B
0
	​

z
^
,E=E
0
	​

cos(kx−ωt+ϕ
0
	​

)
x
^
.

Integração realizada com Runge–Kutta de 4ª ordem (RK4).

Objetivos

Implementar a dispersão fria do modo whistler;

Integrar numericamente o movimento de um elétron;

Analisar o pico de ressonância ciclotrônica;

Realizar varreduras em frequência e fase (Monte Carlo simples);

Aplicar FFT para análise espectral;

Criar gráficos e animações científicos.

Estrutura do Repositório
Projeto_Computacao_Cientifica.ipynb   # Notebook principal
config.json (opcional)                # Parâmetros externos
animations/                           # MP4 das animações (opcional)
README.md                             # Este documento
LICENSE                               # Licença MIT

Como Executar
Instalar dependências:
pip install numpy matplotlib

Executar:

Abra o notebook no Google Colab ou Jupyter e execute célula por célula.
Estão incluídas:

dispersão 
𝑘
(
𝜔
)
k(ω);

simulação da partícula;

varredura 
𝐾
𝑓
(
𝜔
)
K
f
	​

(ω);

FFT;

heatmap;

mini-Vlasov;

animações MP4.

Resultados Obtidos

Curva de dispersão: identifica regiões propagantes;

Órbita helicoidal da partícula com perturbação da onda;

Pico de ressonância em 
𝐾
𝑓
(
𝜔
)
K
f
	​

(ω);

Heatmap mostrando robustez da interação onda–partícula;

FFT confirmando o conteúdo espectral;

Mini-Vlasov revelando evolução no espaço de fase.

Arquitetura Computacional

Integração RK4 estável e reprodutível;

Máscara booleana para descartar regiões com 
𝑛
2
<
0
n
2
<0;

Varreduras otimizadas em frequência e fase;

Conservação de energia validada (teste com 
𝐸
0
=
0
E
0
	​

=0);

Animações exportadas para MP4;

Semente fixa para reprodutibilidade numérica.

Conclusões

O projeto demonstra claramente o mecanismo de ressonância ciclotrônica e seu papel na dinâmica de partículas e ondas em plasmas magnetizados.
Além disso, consolida competências práticas em modelagem, simulação e visualização científica.

Referências

As referências completas encontram-se no arquivo bibliografia.tex presente no Overleaf:

Stix (1992) — Waves in Plasmas

Omura et al. (2008) — Geração de ondas chorus

Helliwell (1965) — Estudos clássicos de whistlers

Chen (2016) — Introdução à física de plasmas

Hunter (2007) — Matplotlib

Licença

Este projeto está sob a MIT License.
Uso livre, desde que citados os autores.
