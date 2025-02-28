# Demo Spring Boot Application

## Sobre
Este projeto foi criado seguindo o tutorial *Spring Quickstart Guide*. Ele contém um simples endpoint `GET /hello` que retorna uma saudação.

## Como Executar

1. Certifique-se de ter o Java e o Maven instalados.
2. Clone este repositório:
   ```sh
   git clone https://github.com/https-Luan-Fernandes/demo
   ```
3. Acesse o diretório do projeto:
   ```sh
   cd demo/demo
   ```
4. Compile e execute o projeto com Maven:
   ```sh
   mvn spring-boot:run
   ```

## Uso

Com o servidor rodando, você pode acessar o endpoint:

- Requisição padrão:
  ```sh
  curl http://localhost:8080/hello
  ```
  **Resposta:**
  ```
  Hello World!
  ```

- Requisição com parâmetro:
  ```sh
  curl http://localhost:8080/hello?name=seu_nome
  ```
  **Resposta:**
  ```
  Hello seu_nome!
  ```

## Código Principal

```java
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
@RestController
public class DemoApplication {

    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }

    @GetMapping("/hello")
    public String hello(@RequestParam(value = "name", defaultValue = "World") String name) {
        return String.format("Hello %s!", name);
    }
}
```

## Licença
Este projeto é de livre uso para estudos e experimentação.

