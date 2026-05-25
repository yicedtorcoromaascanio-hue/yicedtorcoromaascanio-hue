## Hi there 👋

- 🔭 I’m currently working on Algoritmos.
- 🌱 I’m currently learning Python.
- 👯 I’m looking to collaborate on Software.
- 🤔 I’m looking for help with Git.
- 💬 Ask me about Matrices.
- 📫 How to reach me: yicedtorcoromaascanio@gmail.com .
- 😄 Pronouns: yiyi.
- ⚡ Fun fact: curiosidad.

- # 1. Matriz: Lista de listas con al menos 6 productos
# Estructura: [Nombre, Categoría, Precio Base]
menu = [
    ["Ceviche", "Entrada", 18000],
    ["Parrillada", "Plato Fuerte", 55000],
    ["Limonada", "Bebida", 12000],
    ["Malteada", "Bebida", 8500],
    ["Tiramisú", "Postre", 15000],
    ["Vino Tinto", "Bebida", 45000]
]

# Parámetros para la promoción (Umbral y Categoría Objetivo)
categoria_promo = "Bebida"
umbral_precio = 10000

# 2. Módulos: Función para calcular el precio final
def calcular_precio_final(producto, categoria_objetivo, umbral):
    # Descomposición de los datos del producto
    nombre = producto[0]
    categoria = producto[1]
    precio_base = producto[2]
    # Lógica de Negocio: Aplicar 15% de descuento bajo condiciones
    if categoria == categoria_objetivo and precio_base > umbral:
        # Cálculo del descuento: precio * 0.15
        descuento = precio_base * 0.15
        precio_final = precio_base - descuento
    else:
        # Mantener el precio base si no se cumplen las condiciones
        precio_final = precio_base
    return precio_final

# 3. Salida: Mostrar cada producto y sus precios
print("--- RESUMEN DE PRECIOS DEL MENÚ ---")
print(f"{'PRODUCTO':<15} | {'BASE':<10} | {'FINAL':<10}")
print("-" * 40)

for item in menu:
    precio_f = calcular_precio_final(item, categoria_promo, umbral_precio)
    # Formateo de la salida
    print(f"{item[0]:<15} | \({item[2]:<9} | \){precio_f:<9.2f}")
