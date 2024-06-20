# Ciclo de Vida da Activity em Android - N3

- **Nome do Aluno**: Cawan de Melo Santos
- **Curso**: ADS
- **Cadeira**: Desenvolvimento de Aplicações Moveis
- **Faculdade**: Nova Roma Boa Viagem
- **Período**: 4º Período
- **Turno**: Noite

## Introdução

Quando começamos a aprender sobre desenvolvimento de apps mobile no Android, uma das primeiras coisas que ouvimos falar é na Activity. Ela é um componente do Android que representa a tela do nosso aplicativo, onde incluímos itens visuais para interação do usuário, como textos, botões e menus de seleção. O ciclo de vida de uma Activity é gerenciado pelo sistema operacional Android e envolve uma série de callbacks que indicam mudanças no estado da Activity. Compreender esses estados e os métodos de callback é essencial para criar aplicações Android robustas e responsivas.

## Ciclo de Vida da Activity

As Activities no Android têm métodos de callback que permitem transitar por diferentes estados do ciclo de vida à medida que o usuário navega no aplicativo. O ciclo de vida de uma Activity pode ser dividido em quatro estados principais:

1. **Resumed (Executando)**: A Activity está em primeiro plano e interagindo com o usuário.
2. **Paused (Pausada)**: A Activity perdeu o foco, mas ainda está visível.
3. **Stopped (Parada)**: A Activity não está visível, mas ainda está em memória.
4. **Destroyed (Destruída)**: A Activity foi finalizada ou destruída pelo sistema.

### Métodos de Callback

Abaixo estão os principais métodos de callback chamados durante o ciclo de vida de uma Activity:

1. **onCreate(Bundle savedInstanceState)**:
   - Chamado quando a Activity é criada.
   - Inicialização básica deve ser feita aqui.
   - Pode restaurar o estado salvo anteriormente da Activity.

2. **onStart()**:
   - Chamado quando a Activity está prestes a se tornar visível para o usuário.

3. **onResume()**:
   - Chamado quando a Activity começa a interagir com o usuário.
   - A Activity está em primeiro plano.

4. **onPause()**:
   - Chamado quando o sistema está prestes a iniciar outra Activity.
   - Pode ser usado para pausar operações que não precisam continuar enquanto a Activity não está em primeiro plano.

5. **onStop()**:
   - Chamado quando a Activity não está mais visível para o usuário.
   - Pode liberar recursos que não são necessários enquanto a Activity não está visível.

6. **onRestart()**:
   - Chamado quando a Activity está prestes a se tornar visível novamente após ter sido parada.

7. **onDestroy()**:
   - Chamado antes da Activity ser destruída.
   - Permite que a Activity libere todos os recursos que ainda não foram liberados.

## Fluxo das Chamadas

A imagem abaixo representa o fluxo das chamadas de cada callback no ciclo de vida de uma Activity:

![Ciclo de Vida da Activity](https://developer.android.com/images/activity_lifecycle.png)

## Exemplo de Código em Kotlin

```kotlin
package com.example.myapp

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        // Inicialização básica
    }

    override fun onStart() {
        super.onStart()
        // A Activity está prestes a se tornar visível
    }

    override fun onResume() {
        super.onResume()
        // A Activity começou a interagir com o usuário
    }

    override fun onPause() {
        super.onPause()
        // A Activity está prestes a iniciar outra Activity
    }

    override fun onStop() {
        super.onStop()
        // A Activity não está mais visível
    }

    override fun onRestart() {
        super.onRestart()
        // A Activity está prestes a se tornar visível novamente
    }

    override fun onDestroy() {
        super.onDestroy()
        // A Activity está prestes a ser destruída
    }
}
```
## Conclusão

Entender o ciclo de vida da Activity e os métodos de callback é crucial para desenvolver aplicações Android eficientes e responsivas. Cada método tem seu propósito e uso específico, permitindo que os desenvolvedores gerenciem os recursos da aplicação de forma adequada.

## Referências

- [Android: Activity e ciclo de vida - Caio Henrique dos Santos](https://www.linkedin.com/pulse/android-activity-e-ciclo-de-vida-caio-henrique-dos-santos-t5ywf/)
- [Alura: Activity Lifecycle: Por que conhecer o ciclo de vida da Activity?](https://www.alura.com.br/artigos/activity-lifecycle-por-que-conhecer-ciclo-de-vida-activity)
- [Estágios do ciclo de vida da atividade - Android Developers](https://developer.android.com/codelabs/basic-android-kotlin-compose-activity-lifecycle?hl=pt-br#3)
