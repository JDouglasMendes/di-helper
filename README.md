# Codeizi Dependency Injection (DI)

### Instalation

```
dotnet add package Codeizi.DI --version 1.0.0
````

Or

![exemple in manager vs studio](https://github.com/JDouglasMendes/di-helper/blob/master/ManagerDINuget.jpg?raw=true)


### Usage

```C#
[Injectable()]
public class ScopedIndividualService
```
When your class implements interface, can indicate as folows:

```C#
[Injectable(typeof(IContract),typeof(ScopedService))]
public class ScopedService : IContract
```

#### Parameters

Context   | Instance Context                   | Service Add
----------|------------------------------------|----------------------
Scoped    |Default Or InstanceContext.Scoped   | `services.AddScoped`
Transient |InstanceContext.Transient           | `services.AddTransient`
Singleton |InstanceContext.Singleton           | `services.AddSingleton`


```C#
 [Injectable(InstanceContext.Singleton)] 
```
Or

```C#
[Injectable(typeof(ISingletonContract),
    typeof(SingletonService),
    InstanceContext.Singleton)]
```

### In Startup.cs

```C#
 services.AddInjectables(this.GetType().Assembly);
```

### Future Features

- Add multiples attributes in single class.
