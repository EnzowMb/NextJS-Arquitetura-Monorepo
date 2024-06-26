# Arquitetura Front End com NextJS

## Estrutura Base

1. Arquivos de Configuração( . alguma coisa) deve ficar sempre no ponto mais alto do projeto!
2. Configurar workspaces utilizando o ```yarn workspace```
3. Configurar scripts que rodam na raiz do projeto para evitar a navegação em cada pasta sempre que precisar rodar um comando - exemplo:
   
   ```
   "scripts": {
    "web-public": "yarn workspace @alura/web-public",
    "dev:web-public": "yarn web-public dev",
    "build:web-public": "yarn web-public build"
    },
    ```
4. Configurar o módulo desing-system para armazenar os componentes e toda padronização de identidade visual do seu projeto:

   ![image](https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/00d6be00-fcd8-4a53-8e6d-78b939a69338)

5. Trabalhar com next-transpile-modules para fazer a transpilação de nossos módulos e pacotes locais:
   
  ![image](https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/a2934d7c-c2c9-452d-9eba-cd34ff27c2c3)

  ![image](https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/c76189de-5247-412d-96d6-eb653b927c0c)

6. Reusar as configurações do TypeScript criando um módulo setup com a pasta tsconfig-commons e dentro dela nossas configurações em um arquivo base.json

  ![image](https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/6edd989a-5779-4b65-b0f3-315afcd00156)

   base.json:
   ```
     {
    "compilerOptions": {
      "target": "es5",
      "lib": [
        "dom",
        "dom.iterable",
        "esnext"
      ],
      "allowJs": true,
      "skipLibCheck": true,
      "strict": false,
      "forceConsistentCasingInFileNames": true,
      "noEmit": true,
      "incremental": true,
      "esModuleInterop": true,
      "module": "esnext",
      "moduleResolution": "node",
      "resolveJsonModule": true,
      "isolatedModules": true,
      "jsx": "preserve"
    },
    "exclude": ["node_modules"]
    }
  ```

7. Adicionar as configurações recomendadas para o funcionamento correto da lib styled components

-----------------------------------------------
## Configurações de Linter

1. Como configurar o ESLint, Next lint e o Prettier no projeto:

   <img width="310" alt="image" src="https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/077c3b58-d12c-4e54-b1f0-79dfdfc6d0f8">

   Não dar lint em um determinado workspace:

   ![image](https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/8a68e657-d476-4c3a-8812-9881b9f1240d)

   Como colocar lint em um workspace:

   <img width="124" alt="image" src="https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/7af2a065-4de2-4cd3-859d-f5f0ae7bf290">
   
   ![image](https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/a457fb61-e063-43d1-b63e-88875d09010e)
   
   ![image](https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/e7c76c12-7797-40e9-b5d3-a58450bef028)

    <br>

   No package json:<br><br>
   <img width="247" alt="image" src="https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/a5d50759-e3e7-4933-8c71-1ff31f20484d">

    <img width="245" alt="image" src="https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/8eace13b-c9cb-4f4d-a8d6-1b0a267a1b2f">

## CODEOWNERS

Em projetos grandes que utilizam mono-repos, é recomendado deixar uma pessoa da equipe responsável por realizar qualquer ação quando o código mudar. Por exemplo, ao resolver um pull request é muito importante que seja feito um code review, e isso deve ficar a cargo de uma pessoa desenvolvedora.

![image](https://github.com/EnzowMb/NextJS-Arquitetura-Monorepo/assets/89809584/e3b4384e-98ce-4402-a706-86b071d796a2)

