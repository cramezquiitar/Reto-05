# Reto-05
1.Dado la figura de la imagen, desarrolle:
![image](https://github.com/user-attachments/assets/11a768fa-ad67-4f14-adc8-2f6d9e3ff9d0)
Una función matemática para calcular el volumen y el área superficial.
Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r1, r2 y h.
Revise como utilizar el valor de pi usando import math y math.pi
Solucion:
```python
import math

def calcular_volumen(r1: float, r2: float, h: float) -> float:
    """Calcula el volumen total de un hemisferio (r1) más un cono (r2, h)."""
    volumen_hemisferio = (2/3) * math.pi * r1**3
    volumen_cono = (1/3) * math.pi * r2**2 * h
    return volumen_hemisferio + volumen_cono

def calcular_area_superficial(r1: float, r2: float, h: float) -> float:
    """Calcula el área superficial total de un hemisferio más un cono con base."""
    generatriz = math.sqrt(r2**2 + h**2)
    area_hemisferio = 2 * math.pi * r1**2
    area_cono = math.pi * r2 * (r2 + generatriz)  # lateral + base
    return area_hemisferio + area_cono

if __name__ == "__main__":
    r1 = float(input("Ingrese el radio del hemisferio (r1): "))
    r2 = float(input("Ingrese el radio de la base del cono (r2): "))
    h = float(input("Ingrese la altura del cono (h): "))

    volumen = calcular_volumen(r1, r2, h)
    area = calcular_area_superficial(r1, r2, h)

    print("🔹 El volumen total de la figura es:", volumen)
    print("🔹 El área superficial total de la figura es:", area)
```
2.Dado la figura de la imagen, desarrolle:
![image](https://github.com/user-attachments/assets/a91c37ac-a46c-44ff-ab22-77d2e1e7ff87)
Una función matemática para calcular el área y el perimetro.
Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r, a y b.
Revise como utilizar el valor de pi usando import math y math.pi
```python
import math

def calcular_area_total(r: float, a: float, b: float) -> float:
    """Calcula el área total: rectángulo + círculo (2 semicircunferencias superiores)."""
    area_rectangulo = a * b
    area_circulo_superior = math.pi * r**2
    return area_rectangulo + area_circulo_superior

def calcular_perimetro_total(r: float, a: float, b: float) -> float:
    """Calcula el perímetro total de la figura con parte superior redondeada."""
    perimetro_lados = 2 * a + b
    perimetro_curva_superior = 2 * math.pi * r
    return perimetro_lados + perimetro_curva_superior

if __name__ == "__main__":
    r = float(input("Ingrese el radio de la parte superior curva (r): "))
    a = float(input("Ingrese la altura del rectángulo (a): "))
    b = float(input("Ingrese la base del rectángulo (b): "))

    area = calcular_area_total(r, a, b)
    perimetro = calcular_perimetro_total(r, a, b)

    print("🔹 El área total de la figura es:", area)
    print("🔹 El perímetro total de la figura es:", perimetro)
```
3.Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.
```python
def calcular_carne_aves(n_gallinas: int, m_gallos: int, k_pollitos: int) -> int:
    """
    Calcula la cantidad total de carne de aves en kilogramos.
    
    Parámetros:
    - n_gallinas: número de gallinas
    - m_gallos: número de gallos
    - k_pollitos: número de pollitos
    
    Retorna:
    - Cantidad total de carne en kg
    """
    peso_total = (n_gallinas * 6) + (m_gallos * 7) + (k_pollitos * 1)
    return peso_total


if __name__ == "__main__":
    n = int(input("Ingrese la cantidad de gallinas: "))
    m = int(input("Ingrese la cantidad de gallos: "))
    k = int(input("Ingrese la cantidad de pollitos: "))

    total_kg = calcular_carne_aves(n, m, k)
    print(f"🔸 La cantidad total de carne es: {total_kg} kg")
```
4.Haga un programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.
```python
def calcular_valor_prestamo(C: float, i: float, n: int) -> float:
    """
    Calcula el valor futuro de un préstamo con interés compuesto.

    Parámetros:
    - C: capital inicial
    - i: tasa de interés mensual (por ejemplo, 0.05 para 5%)
    - n: número de meses

    Retorna:
    - Valor final del préstamo
    """
    return C * (1 + i) ** n

if __name__ == "__main__":
    C = float(input("Ingrese el monto del préstamo (capital inicial): "))
    i = float(input("Ingrese la tasa de interés mensual (por ejemplo, 0.05 para 5%): "))
    n = int(input("Ingrese el número de meses: "))

    valor_final = calcular_valor_prestamo(C, i, n)
    print(f"📈 El valor final del préstamo después de {n} meses es: {valor_final:.2f}")
```
5.Escriba un programa que pida 5 números reales y calcule las siguientes operaciones usando una función para cada una:
```python
def pedir_numeros():
    print("Ingrese 5 números reales:")
    n1 = float(input("Número 1: "))
    n2 = float(input("Número 2: "))
    n3 = float(input("Número 3: "))
    n4 = float(input("Número 4: "))
    n5 = float(input("Número 5: "))
    return n1, n2, n3, n4, n5

def calcular_promedio(a, b, c, d, e):
    return (a + b + c + d + e) / 5

def promedio_multiplicativo(a, b, c, d, e):
    producto = a * b * c * d * e
    return producto ** (1 / 5)

def obtener_mayor_y_menor(a, b, c, d, e):
    mayor = menor = a
    for valor in (b, c, d, e):
        if valor > mayor:
            mayor = valor
        if valor < menor:
            menor = valor
    return mayor, menor

def potencia_mayor_al_menor(mayor, menor):
    return mayor ** menor

def raiz_cubica_menor(menor):
    if menor >= 0:
        return menor ** (1 / 3)
    else:
        return -(-menor) ** (1 / 3)  # para negativos

if __name__ == "__main__":
    n1, n2, n3, n4, n5 = pedir_numeros()

    promedio = calcular_promedio(n1, n2, n3, n4, n5)
    promedio_mult = promedio_multiplicativo(n1, n2, n3, n4, n5)
    mayor, menor = obtener_mayor_y_menor(n1, n2, n3, n4, n5)
    potencia = potencia_mayor_al_menor(mayor, menor)
    raiz_cubica = raiz_cubica_menor(menor)

    print("\nResultados:")
    print("Promedio:", promedio)
    print("Promedio multiplicativo:", promedio_mult)
    print("Potencia del mayor elevado al menor:", potencia)
    print("Raíz cúbica del menor número:", raiz_cubica)
```
6.
¿Qué es pip en Python?
pip es la herramienta oficial para instalar y gestionar paquetes de Python. Permite descargar, instalar, actualizar y desinstalar bibliotecas desde el repositorio PyPI (Python Package Index).

¿Cómo funciona?
Al ejecutar un comando como pip install nombre_paquete, pip descarga el paquete desde PyPI, lo instala en tu comutador y resuelve automáticamente las dependencias necesarias.

Ejemplo básico:
```
pip install requests
```
Esto instalará la biblioteca requests para hacer peticiones HTTP.
7.
requests

Uso: Para hacer solicitudes HTTP fáciles y eficientes.

Instalación: pip install requests

numpy

Uso: Para cálculo numérico y manejo de arreglos multidimensionales.

Instalación: pip install numpy

pandas

Uso: Para manipulación y análisis de datos.

Instalación: pip install pandas

matplotlib

Uso: Para crear gráficos y visualizaciones.

Instalación: pip install matplotlib

scikit-learn

Uso: Para machine learning y análisis predictivo.

Instalación: pip install scikit-learn

flask

Uso: Framework ligero para desarrollo web.

Instalación: pip install flask

django

Uso: Framework completo para desarrollo web.

Instalación: pip install django

beautifulsoup4

Uso: Para parsing y scraping de HTML y XML.

Instalación: pip install beautifulsoup4

pytest

Uso: Framework para pruebas unitarias.

Instalación: pip install pytest

tensorflow

Uso: Biblioteca para machine learning y deep learning.

Instalación: pip install tensorflow
para instalarlo en python:
```
pip install nombre_del_modulo
```
