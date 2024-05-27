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
