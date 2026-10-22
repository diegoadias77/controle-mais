# Controle+ · viva melhor: como publicar e instalar

## O que tem na pasta

| Arquivo | Função |
|---|---|
| `index.html` | O app completo |
| `manifest.webmanifest` | Nome, ícone e cores usados na instalação |
| `sw.js` | Faz o app abrir sem internet |
| `icons/` | Ícones do app para Android e iPhone |

## 1. Publicar no GitHub Pages (gratuito, cerca de 10 minutos)

1. Crie uma conta em **github.com**, se ainda não tiver.
2. Clique em **+ → New repository**.
   - Nome: `controle-mais`
   - Marque **Public**. O GitHub Pages gratuito exige repositório público, mas os seus registros **não** vão para lá: eles ficam só no celular.
   - Clique em **Create repository**.
3. Na página do repositório, clique em **uploading an existing file**. Arraste o **conteúdo** da pasta: `index.html`, `manifest.webmanifest`, `sw.js` e a pasta `icons`. Clique em **Commit changes**.
4. Vá em **Settings → Pages**. Em *Branch*, escolha `main` e a pasta `/ (root)`, e clique em **Save**.
5. Em 1 ou 2 minutos o endereço aparece no topo da página:
   `https://SEU-USUARIO.github.io/controle-mais/`

**Alternativa ainda mais rápida:** em **app.netlify.com/drop**, arraste a pasta inteira. O Netlify gera um endereço na hora. Crie uma conta para o site não expirar.

## 2. Instalar no celular

- **Android (Chrome):** abra o endereço, toque em ⋮ → **Instalar app** (ou **Adicionar à tela inicial**).
- **iPhone (Safari):** abra o endereço, toque em **Compartilhar → Adicionar à Tela de Início**.

Depois de instalado, o app abre em tela cheia e funciona sem internet.

## 3. Backup: importante

Os dados ficam **só no aparelho**. Se você desinstalar o app, limpar os dados do navegador ou trocar de celular, os registros são apagados.

- Em **Ajustes → Fazer backup**, o app gera um arquivo `.json`. Salve esse arquivo no Google Drive, no e-mail ou no WhatsApp.
- O app mostra um lembrete na tela Hoje quando o último backup tem mais de 7 dias.
- Para trocar de celular: instale o app no aparelho novo e use **Ajustes → Restaurar backup**.

## 4. Atualizar o app depois

Quando eu enviar uma nova versão do `index.html`:

1. Substitua o arquivo no GitHub (**Add file → Upload files**).
2. No `sw.js`, aumente o número em `const VERSION = 'v8'` (para `'v9'`, depois `'v10'`, e assim por diante). Os arquivos que eu envio já vêm com a versão trocada.
3. Feche e abra o app duas vezes para ele pegar a versão nova.

Os seus registros não são afetados pela atualização.

## 5. Foto do prato (chave de API)

1. Crie uma conta em **console.anthropic.com**.
2. Em **Billing**, adicione créditos (mínimo de US$ 5).
3. Em **Settings → Limits**, defina um limite de gasto mensal.
4. Em **API keys → Create key**, crie a chave e copie-a.
5. No app, vá em **Ajustes → Foto do prato (IA)**, cole a chave e toque em **Salvar chave**. O app testa a chave sozinho.

A chave fica só no aparelho e não entra no backup. Cadastre a chave em cada aparelho onde for usar a foto.

## 6. Lembretes (água, refeições, peso e aplicação)

1. No app, vá em **Ajustes → Lembretes**, ajuste os horários e toque em **Baixar arquivo de lembretes**.
2. **Android:** no computador, abra **calendar.google.com** → Configurações → **Criar nova agenda** chamada *Controle+* → em *Notificações de eventos*, coloque **Notificação, 0 minutos** → **Importar e exportar** → escolha o arquivo e a agenda *Controle+*.
3. **iPhone:** abra o arquivo no celular e toque em **Adicionar todos**.

Os avisos chegam pelo Google Agenda ou pelo Calendário, mesmo com o app fechado. Cada aviso traz um link que abre o app direto na parte certa (água, refeições, peso ou doses).

Para mudar os horários: exclua a agenda *Controle+*, crie de novo e importe o arquivo novo.

## 7. Evolução (check-in mensal)

- **Perfil:** em Ajustes → Seu perfil, adicione sua foto e como quer ser chamado.
- **Check-in:** na aba **Evolução → Novo check-in**, tire 3 fotos (frente, lado e costas) e anote as medidas com fita métrica.
- **Comparação:** escolha dois check-ins e compare as fotos deslizando ou lado a lado, com a tabela de diferenças.
- **Indicadores:** cintura ÷ altura, cintura ÷ quadril, % de gordura (método da Marinha americana) e IMC.
- **PIN:** em Ajustes → Privacidade, crie um PIN de 4 dígitos para proteger a aba Evolução.
- As fotos ficam só no aparelho. O backup inclui as fotos se a opção estiver marcada.

## 8. Personalizar

No `index.html`, procure estas linhas:

- `const FOODS=[...]`: os botões de alimentos. Cada item tem o nome (`n`) e os gramas de proteína (`p`).
- `const SYMPTOMS=[...]`: a lista de sintomas.
- `const DEFAULT_CFG={...}`: as metas iniciais de proteína (g) e água (ml).

## 9. Próximo passo opcional: APK para Android

Com o app publicado, entre em **pwabuilder.com**, cole o endereço e escolha **Package for stores → Android**. O site gera um APK que você pode instalar direto no celular.
