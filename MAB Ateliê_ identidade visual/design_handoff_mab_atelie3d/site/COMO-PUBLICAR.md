# Como publicar mabatelie3d.com.br na Vercel

O arquivo `index.html` desta pasta e o site inteiro — um unico arquivo, sem
dependencia de nada. Da para abrir com dois cliques para conferir antes de subir.

## 1. Subir para a Vercel

Caminho mais simples, sem instalar nada:

1. Crie uma conta em vercel.com (pode entrar com o Google).
2. Va em vercel.com/new e escolha a opcao de importar de um repositorio Git.
   Se voce nao usa Git, use o caminho do terminal abaixo, que e mais direto.

Caminho pelo terminal (funciona de primeira):

1. Instale o Node.js (nodejs.org) se ainda nao tiver.
2. Abra o terminal (Prompt de Comando no Windows) e rode:

       npm i -g vercel

3. Entre na pasta que contem o index.html:

       cd caminho/para/a/pasta/site

4. Rode:

       vercel

   Ele pergunta o nome do projeto e se e um projeto novo. Aceite os padroes.
   No fim ele mostra um endereco .vercel.app — o site ja esta no ar.

5. Para publicar em producao:

       vercel --prod

## 2. Ligar o dominio mabatelie3d.com.br

1. No painel da Vercel, abra o projeto e va em Settings > Domains.
2. Clique em Add e digite: mabatelie3d.com.br
3. Adicione tambem: www.mabatelie3d.com.br
4. A Vercel vai mostrar na tela os valores de DNS que voce precisa cadastrar.
   Normalmente e:
      - um registro A para o dominio raiz, apontando para o IP que ela informar
      - um CNAME para o www, apontando para cname.vercel-dns.com
   Use exatamente os valores que a tela da Vercel mostrar, nao os de outro tutorial.
5. Entre no painel de onde voce comprou o dominio (Registro.br, Hostinger,
   GoDaddy, o que for), procure "DNS" ou "Zona DNS" e cadastre esses registros.
6. A propagacao leva de alguns minutos a algumas horas. A Vercel emite o
   certificado HTTPS sozinha depois que o DNS estiver certo.

## 3. Cuidado com o e-mail

Ao mexer no DNS, NAO apague os registros MX nem o TXT de SPF/DKIM — sao eles
que fazem o mab.atelie@mabatelie3d.com.br funcionar. Mexa somente no registro A
e no CNAME do www.

## 4. Quando as fotos estiverem prontas

Me mande as fotos das pecas e eu troco a foto da pagina, monto a galeria e,
quando voce quiser, transformo em loja. Ai voce roda `vercel --prod` de novo
com o arquivo novo e o site atualiza.
