# Framework_Python_POO
Actividad en clase

#Codigo 1

print(" ")

print("Dylan Aaron Elicserio Martínez 3°W #Control:1179")

print(" ")

class Persona:

    """
    
    Clase para representar una persona.
    
    Atributos:
    
        - nombre: str (opcional)
        
        - edad: int (opcional)
        
        - dni: str (opcional)
        
    Métodos:
    
        - mostrar: Muestra los datos de la persona.
        
        - esMayorDeEdad: Devuelve True si la persona es mayor de edad, False en caso contrario.
        
    """

    def __init__(self, nombre="", edad=0, dni=""):
    
        self.__nombre = nombre
        
        self.__edad = edad
        
        self.__dni = dni

    # Getters y setters con validación
    
    @property
    
    def nombre(self):
    
        return self.__nombre

    @nombre.setter
    
    def nombre(self, valor):
    
        if isinstance(valor, str) and valor.strip():
        
            self.__nombre = valor
            
        else:
        
            raise ValueError("El nombre debe ser una cadena no vacía.")

    @property
    
    def edad(self):
    
        return self.__edad
        

    @edad.setter
    
    def edad(self, valor
    
    ):
        if isinstance(valor, int) and valor >= 0:
        
            self.__edad = valor
            
        else:
        
            raise ValueError("La edad debe ser un entero no negativo.")

    @property
    
    def dni(self):
    
        return self.__dni

    @dni.setter
    
    def dni(self, valor):
    
        if isinstance(valor, str) and valor.strip():
        
            self.__dni = valor
            
        else:
        
            raise ValueError("El DNI debe ser una cadena no vacía.")

    def mostrar(self):
    
        return f"Nombre: {self.__nombre}, Edad: {self.__edad}, DNI: {self.__dni}"

    def esMayorDeEdad(self):
    
        return self.__edad >= 18


# Prueba del programa

persona = Persona("Pepe", 28, "12345678Z")

print(persona.mostrar())

print(f"¿Es mayor de edad? {persona.esMayorDeEdad()}")

![image](https://github.com/user-attachments/assets/a3cfa3d9-dddc-43a0-8ad2-450a3371a10f)

![image](https://github.com/user-attachments/assets/1a1030a0-33f1-4f77-a60a-f62ada7ad2ad)

#Codigo 2

print(" ")

print("Dylan Aaron Elicserio Martínez 3°W #Control:1179")

print(" ")

class Persona:

    def __init__(self, nombre="", edad=0, dni=""):
    
        self.nombre = nombre
        
        self.edad = edad
        
        self.dni = dni
        
    @property
    
    def nombre(self):
    
        return self._nombre
        
    @nombre.setter
    
    def nombre(self, value):
    
        if not isinstance(value, str):
        
            raise ValueError("El nombre debe ser una cadena de texto.")
            
        self._nombre = value
        
    @property
    
    def edad(self):
    
        return self._edad
        
    @edad.setter
    
    def edad(self, value):
    
        if not isinstance(value, int) or value < 0:
        
            raise ValueError("La edad debe ser un entero positivo.")
            
        self._edad = value
        
    @property
    
    def dni(self):
    
        return self._dni
        
    @dni.setter
    
    def dni(self, value):
    
        if not isinstance(value, str) or len(value) != 9:
        
            raise ValueError("El DNI debe ser una cadena de 9 caracteres.")
            
        self._dni = value
        
    def mostrar(self):
    
        return f"Nombre: {self.nombre}, Edad: {self.edad}, DNI: {self.dni}"
        
class Cuenta:

    def __init__(self, titular, cantidad=0.0):
    
        # Validar que titular sea una instancia de Persona
        
        if not isinstance(titular, Persona):
        
            raise ValueError("El titular debe ser una instancia de la clase Persona.")
            
        self.titular = titular
        
        self._cantidad = float(cantidad)
        
    @property
    
    def cantidad(self):
    
        return self._cantidad
        
    def ingresar(self, cantidad):
    
        # Solo permite ingresar cantidades positivas
        
        if cantidad > 0:
        
            self._cantidad += cantidad
            
    def retirar(self, cantidad):
    
        # Permite retirar cualquier cantidad, incluso dejando saldo negativo
        
        self._cantidad -= cantidad
        
    def mostrar(self):
    
        # Devuelve un mensaje con los datos de la cuenta
        
        return f"Titular: {self.titular.mostrar()}, Cantidad: {self.cantidad:.2f}"
        
# Ejemplo de uso

try:

    persona1 = Persona("Juan Pérez", 30, "12345678A")
    
    cuenta = Cuenta(persona1, 500.0)
    
    print(cuenta.mostrar())  # Mostrar datos iniciales
    
    cuenta.ingresar(200)     # Ingresar 200
    
    cuenta.retirar(100)      # Retirar 100
    
    print(cuenta.mostrar())  # Mostrar datos actualizados
    
except Exception as e:

    print(f"Error: {e}")
    
![image](https://github.com/user-attachments/assets/ad4ddebe-8853-4234-8639-b614f392308d)

![image](https://github.com/user-attachments/assets/d69065af-fb42-4e42-b3bc-9bead107c128)

#Codigo 3

print(" ")

print("Dylan Aaron Elicserio Martínez 3°W #Control:1179")

print(" ")

class Persona:

    def __init__(self, nombre="", edad=0, dni=""):
    
        self.nombre = nombre
        
        self.edad = edad
        
        self.dni = dni
        
    @property
    
    def nombre(self):
    
        return self._nombre
        
    @nombre.setter
    
    def nombre(self, value):
    
        if not isinstance(value, str):
        
            raise ValueError("El nombre debe ser una cadena de texto.")
            
        self._nombre = value
        
    @property
    
    def edad(self):
    
        return self._edad
        
    @edad.setter
    
    def edad(self, value):
    
        if not isinstance(value, int) or value < 0:
        
            raise ValueError("La edad debe ser un entero positivo.")
            
        self._edad = value
        
    @property
    
    def dni(self):
    
        return self._dni
        
    @dni.setter
    
    def dni(self, value):
    
        if not isinstance(value, str) or len(value) != 9:
        
            raise ValueError("El DNI debe ser una cadena de 9 caracteres.")
            
        self._dni = value
        
    def mostrar(self):
    
        return f"Nombre: {self.nombre}, Edad: {self.edad}, DNI: {self.dni}"
        
    def esMayorDeEdad(self):
    
        return self.edad >= 18
        
class Cuenta:

    def __init__(self, titular, cantidad=0.0):
    
        if not isinstance(titular, Persona):
        
            raise ValueError("El titular debe ser una instancia de la clase Persona.")
            
        self.titular = titular
        
        self._cantidad = float(cantidad)
        
    @property
    
    def cantidad(self):
    
        return self._cantidad
        
    def ingresar(self, cantidad):
    
        if cantidad > 0:
        
            self._cantidad += cantidad
            
    def retirar(self, cantidad):
    
        self._cantidad -= cantidad
        
    def mostrar(self):
    
        return f"Titular: {self.titular.mostrar()}, Cantidad: {self.cantidad:.2f}"
        
class CuentaJoven(Cuenta):

    def __init__(self, titular, cantidad=0.0, bonificacion=0.0):
    
        super().__init__(titular, cantidad)
        
        self.bonificacion = bonificacion
        
    @property
    
    def bonificacion(self):
    
        return self._bonificacion
        
    @bonificacion.setter
    
    def bonificacion(self, value):
    
        if not isinstance(value, (int, float)) or value < 0:
        
            raise ValueError("La bonificación debe ser un número positivo.")
            
        self._bonificacion = value

    def esTitularValido(self):
    
        return self.titular.esMayorDeEdad() and self.titular.edad < 25
        
    def retirar(self, cantidad):
    
        if self.esTitularValido():
        
            super().retirar(cantidad)
            
        else:
        
            raise PermissionError("El titular no es válido para retirar dinero.")
            
    def mostrar(self):
    
        return (f"Cuenta Joven\nTitular: {self.titular.mostrar()}, "
        
                f"Cantidad: {self.cantidad:.2f}, Bonificación: {self.bonificacion}%")
                
try:

    persona1 = Persona("Ana López", 22, "87654321B")  # Titular válido
    }
    cuenta_joven = CuentaJoven(persona1, 1500.0, 5.0)  # Creación de Cuenta Joven
    
    print(cuenta_joven.mostrar())  # Mostrar datos iniciales
    
    cuenta_joven.ingresar(500)     # Ingresar 500
    
    cuenta_joven.retirar(300)      # Retirar 300
    
    print(cuenta_joven.mostrar())  # Mostrar datos actualizados
    
    persona2 = Persona("Carlos Sánchez", 30, "12345678C")  # Titular no válido
    
    cuenta_joven_no_valida = CuentaJoven(persona2, 2000.0, 3.0)
    
    cuenta_joven_no_valida.retirar(100)  # Esto generará un error
    
except Exception as e:

    print(f"Error: {e}")

![image](https://github.com/user-attachments/assets/fb782b36-a158-4297-bad4-adfcc4eccde3)

![image](https://github.com/user-attachments/assets/e514aeb8-d554-4be0-811f-872cca3d74a5)
