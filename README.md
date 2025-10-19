# Proxy
```cs
interface IService { void Request(); }

class RealService : IService { public void Request()=>Console.WriteLine("Real Service"); }

class Proxy : IService {
    private RealService _service;
    public void Request(){
        _service ??= new RealService();
        Console.WriteLine("Proxy control");
        _service.Request();
    }
}

class Program { static void Main()=>new Proxy().Request(); }
