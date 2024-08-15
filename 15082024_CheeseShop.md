### Cheese.java

```java
package com.datorium.Datorium.API.DTOs;

public class Cheese {

    public String name;
    public int price;
    public String kind;
}
```

### CheeseShopRepository.java

```java
package com.datorium.Datorium.API.Repo;

import com.datorium.Datorium.API.DTOs.Cheese;
import java.util.ArrayList;

public class CheeseShopRepository {

    private ArrayList<Cheese> cheeses = new ArrayList<>();

    public int add(Cheese cheese) {
        cheeses.add(cheese);
        return cheeses.size();
    }

    public ArrayList<Cheese> get() {
        return cheeses;
    }

    public Cheese update(int cheeseIndex, Cheese updateCheeseDTO) {
        var cheese = cheeses.get(cheeseIndex);
        cheese.name = updateCheeseDTO.name;
        cheese.price = updateCheeseDTO.price;
        cheese.kind = updateCheeseDTO.kind;

        return cheese;
    }
}
```
### CheeseShopService.java

```java
package com.datorium.Datorium.API.Services;

import com.datorium.Datorium.API.DTOs.Cheese;
import com.datorium.Datorium.API.Repo.CheeseShopRepository;


import java.util.ArrayList;

public class CheeseShopService {
    private CheeseShopRepository cheeseShopRepository;

    public CheeseShopService() {
        cheeseShopRepository = new CheeseShopRepository();
    }

    public int add(Cheese cheese) {
        return cheeseShopRepository.add(cheese);
    }

    public ArrayList<Cheese> get() {
        return cheeseShopRepository.get();
    }

    public Cheese update(int cheeseIndex, Cheese updateCheeseDTO) {
        return cheeseShopRepository.update(cheeseIndex, updateCheeseDTO);

    }
}
```

### CheeseShopController.java

```java
package com.datorium.Datorium.API.Controllers;

import com.datorium.Datorium.API.DTOs.Cheese;
import com.datorium.Datorium.API.DTOs.UpdateCheeseDTO;
import com.datorium.Datorium.API.Services.CheeseShopService;
import org.springframework.web.bind.annotation.*;

import java.util.ArrayList;

@RestController
@RequestMapping("/cheese")
public class CheeseShopController {
    private CheeseShopService cheeseShopService;

    public CheeseShopController() {
        cheeseShopService = new CheeseShopService();
    }

    @PostMapping("/add") 
    public int add(@RequestBody Cheese cheese) {
        return cheeseShopService.add(cheese);
    }

    @GetMapping("/get")
    public ArrayList<Cheese> get() {
        return cheeseShopService.get();
    }

    @PostMapping("/update")
    public Cheese update(@RequestBody UpdateCheeseDTO updateCheeseDTO) {
        return cheeseShopService.update(updateCheeseDTO.cheeseIndex, updateCheeseDTO.cheese);
    }

}
```

### UpdateCheeseDTO.java

```java
package com.datorium.Datorium.API.DTOs;

public class UpdateCheeseDTO {
    public Cheese cheese;
    public int cheeseIndex;

}
```

### POST http://localhost:8080/cheese/add

```json
{
    "name": "Holland",
    "price": 7,
    "kind": "medium"
}
```

### POST http://localhost:8080/cheese/update

```json
{
    "cheeseIndex": 1,
    "cheese": 
        {"name": "Brie",
        "price": 11,
        "kind" : "soft"}
}
```
