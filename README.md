# PresençaQR • Gestão Acadêmica

Protótipo frontend do **Sistema de Registro de Presença Acadêmica com QR Code Dinâmico**
(Engenharia de Software · UMC · 2026). Um único arquivo: `index.html`
(HTML5 + Tailwind CSS via CDN + JavaScript puro + Lucide Icons + QRCode.js).

## Como rodar

Abra `index.html` no Chrome, Edge ou Firefox. É preciso internet para carregar os CDNs.
Para testar a câmera de verdade, sirva por HTTPS ou `localhost` (ex.: `npx serve .`),
porque os navegadores bloqueiam a câmera em páginas sem contexto seguro.

- Senha de todas as contas demo: `umc2026`
- Acesso rápido: botões na tela de login ou o seletor **Perfil demo** no topo
- **Resetar dados demo** (rodapé) recria a base com datas a partir de hoje. Use antes de apresentar.

## Roteiro de demonstração

1. **Portal:** tente entrar com o aluno inativo (Matheus Messias) para ver o bloqueio RN01.
2. **Aluno (Felipe):** use o simulador: leitura válida, válida de novo (RN08), token expirado e turma não vinculada.
3. **Professor (Prof.ª Vanessa):** retome a chamada ao vivo de ESW-401, abra o modo projeção, lance uma presença manual, encerre a chamada e veja o histórico com o bloqueio de 7 dias (RN12).
4. **Admin:** reative o Matheus, crie usuário/disciplina/turma, filtre o relatório e exporte o CSV.
5. **Tempo real:** abra o professor em uma aba e o aluno em outra (mesmo navegador). A lista do professor atualiza sozinha.

## Limitações conhecidas (é um protótipo sem servidor)

- Os dados ficam no `localStorage` do navegador. **Celular e projetor não conversam entre si**:
  a validação entre dispositivos exige o backend (Spring Boot + MySQL) descrito no projeto.
- O hash de senha (SHA-256 com salt) é só demonstrativo; no backend use BCrypt (RNF-P03).
- O tempo de validação exibido é medido localmente e não comprova o RNF-P01 (60 alunos simultâneos).
