## 📌 Descrição Geral

Este programa em Kotlin calcula o **preço do ingresso de cinema** com base em duas condições:

* **Idade da pessoa**.
* **Se o dia da semana é segunda-feira** (com desconto).

Ele imprime o valor do ingresso para diferentes faixas etárias (criança, adulto e idoso).

---

## 📂 Estrutura do Código

### Função `main()`

```kotlin
fun main() {
    val child = 5
    val adult = 28
    val senior = 87
    
    val isMonday = true
    
    println("The movie ticket price for a person aged $child is \$${ticketPrice(child, isMonday)}.")
    println("The movie ticket price for a person aged $adult is \$${ticketPrice(adult, isMonday)}.")
    println("The movie ticket price for a person aged $senior is \$${ticketPrice(senior, isMonday)}.")
}
```

* **Objetivo**: Ponto de entrada do programa.
* **O que faz**:

  * Define três variáveis de idade: criança (`5`), adulto (`28`) e idoso (`87`).
  * Define se é segunda-feira (`isMonday = true`).
  * Para cada idade, chama a função `ticketPrice()` e imprime o preço correspondente.

#### 🔑 Variáveis

* `child = 5` → idade de uma criança.
* `adult = 28` → idade de um adulto.
* `senior = 87` → idade de um idoso.
* `isMonday = true` → indica que é segunda-feira.

---

### Função `ticketPrice(age: Int, isMonday: Boolean): Int`

```kotlin
fun ticketPrice(age: Int, isMonday: Boolean): Int {
    if(age <= 12) {
        return 15
    } else if(age > 12 && age <= 60) {
        if(isMonday) {
            return 25
        } else {
            return 30
        }
    } else if(age > 60 && age <= 100) {
        return 20
    } else {
        return -1
    }
}
```

* **Objetivo**: Retorna o preço do ingresso com base na idade e no dia da semana.
* **Parâmetros**:

  * `age: Int` → idade da pessoa.
  * `isMonday: Boolean` → indica se é segunda-feira (true/false).
* **Retorno**:

  * `15` → preço para crianças (≤ 12 anos).
  * `25` → preço para adultos até 60 anos em segunda-feira.
  * `30` → preço para adultos até 60 anos em outros dias.
  * `20` → preço para idosos (entre 61 e 100 anos).
  * `-1` → caso a idade não seja válida (negativa ou acima de 100).

---

## 📊 Fluxo de Execução

1. O programa começa em `main()`.
2. São definidas três idades e o dia da semana (`isMonday = true`).
3. Para cada idade, chama-se `ticketPrice()`:

   * `child = 5` → retorna **15**.
   * `adult = 28` (segunda-feira) → retorna **25**.
   * `senior = 87` → retorna **20**.
4. As mensagens são exibidas no console.

---

## ✅ Exemplo de Saída (quando `isMonday = true`)

```
The movie ticket price for a person aged 5 is $15.
The movie ticket price for a person aged 28 is $25.
The movie ticket price for a person aged 87 is $20.
```

---
