
---

````ad-quote
title:
```ad-quote
title:
###### **Inicia Aplicação Python** 
```

```python
def printHeader():
    print("\n\n| *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *\n\n")

def main():
    printHeader()
    print("Hello, World!")

if __name__ == "__main__":
    main()
```



````

---

>[!example] **New**

---

````ad-quote
title:
```ad-quote
title:
###### **Abre o File Explorer** 
```

```python
import tkinter as tk
from tkinter import filedialog

def selecionar_arquivo():
    root = tk.Tk()
    root.withdraw()

    caminho_do_arquivo = filedialog.askopenfilename()
    
    return caminho_do_arquivo

if __name__ == "__main__":
    print("Iniciando o seletor de arquivos...")
    
    arquivo_selecionado = selecionar_arquivo()

    if arquivo_selecionado:
        print(f"\n✅ Arquivo selecionado com sucesso!")
        print(f"O caminho do arquivo é: {arquivo_selecionado}")

    else:
        print("\n❌ Nenhuma seleção foi feita. O programa foi encerrado.")

```



````

---

