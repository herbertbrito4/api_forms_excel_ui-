# Recebimento de NFs🚀

[![Integration](https://img.shields.io/badge/Integration-Google_Forms-blue)](https://forms.google.com)
[![Status](https://img.shields.io/badge/Status-Functional-success)](https://github.com/)

## Demo online (https://herbertbrito4.github.io/api_forms_excel_ui-/Index.html)

O projeto uma interface personalizada (Frontend) de alta performance e estilo "Terminal UI", projetada para substituir a interface padrão do Google Forms em processos de recebimento de Notas Fiscais. 

## 🎯 O Problema
O Google Forms nativo possui limitações estéticas e de usabilidade para fluxos operacionais rápidos. Além disso, lidar com formulários que possuem *muitas seções e lógicas condicionais* via requisição direta (POST) é complexo, pois o Google exige a validação do histórico de navegação (pageHistory).

## 💡 A Solução
Este projeto utiliza uma técnica de *Post Direct Injection*. Ele simula o comportamento de um formulário multi-páginas em uma interface única (Single Page Application), enviando todos os dados de uma vez através de um iframe oculto, ignorando as transições de página nativas do Google.

### Diferenciais:
* *Lógica de Cascata Avançada:* Campos de conferência e divergência só aparecem via gatilhos específicos (JS).
* *Controle de Sessão:* Manipulação dinâmica do parâmetro pageHistory e fbzx para garantir a integração com formulários segmentados.
* *Zero Redirect:* O usuário nunca sai da interface; o envio é processado em segundo plano.
* *UI Retro-Futurista:* Inspirada em terminais de logística dos anos 80/90, otimizada para foco total.

## 🛠️ Tecnologias
* *HTML5/CSS3:* Estrutura e estilização com variáveis CSS e fontes Google (Syne & JetBrains Mono).
* *JavaScript (Vanilla):* Lógica de visibilidade condicional e interceptação de POST.
* *Google Forms:* Backend (Database) para armazenamento das respostas.

## 🚀 Como usar
1.  Abra o arquivo index.html.
2.  Preencha os dados do Solicitante e NF.
3.  Observe que o campo de *Conferência Física* só será desbloqueado se o responsável for *TERCEIROS*.
4.  Clique em *FINALIZAR_REGISTRO* para enviar os dados diretamente para a planilha do Google Sheets vinculada.

## ⚙️ Configuração Técnica
Para replicar este projeto em outro formulário, é necessário mapear os entry.IDs no inspecionador de elementos do Google Forms original:

```html
<input type="hidden" name="entry.1680170285" value="Solicitante">
<input type="hidden" name="pageHistory" value="0,1,2,3">
