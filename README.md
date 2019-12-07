# dyn-forms

```bash
node -v
v10.17.0
npm -v
6.13.2
npm i lerna@2.9.0 -g
mkdir -p ~/Desktop/Development/components/monorepo/dyn-forms
cd ~/Desktop/Development/components/monorepo/dyn-forms
lerna init
cd packages
mkdir alpha
mkdir beta
mkdir usage
```

Para cada um dos diretórios de pacote fazer:

```bash
npm init -y
```

Isso criará os arquivos package.json simplificados

Ou seja:

```bash
for a in alpha beta usage 
do 
   echo •••• $a 
   cd $a
   npm init -y
   cd -
done
```

```bash
echo "module.exports = 'alpha'" > alpha/index.js
echo "module.exports = 'beta'"  > beta/index.js
echo "var alpha = require('alpha'); var beta = require('beta'); console.log(alpha + ' ' + beta)" > usage/index.js
```

```bash
node ./packages/usage/index.js 
```

