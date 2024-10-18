# Estudo de comandos NASM

<p align="center">
<img src="https://seeklogo.com/images/N/netwide-assembler-nasm-logo-EC5B1109AC-seeklogo.com.png" width=200px height=200px>
</p>

## Primeiro comandos 

* Programa hello world

```Assembly
global _start

    section .text
    _start:
        mov rax,1               ; prepara o sistema para fazer a escrita de texto
        mov rdi,1               ; preparar a saida do texto na tela
        mov rsi,mensagem        ; imprimir ou exibir a mensagem na tela
        mov rdx,13              ; quantidade de caracteres
        syscall                 ; chama o sistema para preparar a saida
        mov rax,60              ; chamada para a saida do sistema
        xor rdi,rdi             ; executar a saida do sistema
        syscall                 ; invocar o sistema operacional para fechar

        section data 
        mensagem:db 'Hello,World', 10     ; o valor 10 representa a quedra de linha
```