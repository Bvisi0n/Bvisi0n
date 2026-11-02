# Unity Conventions

## Naming Conventions
| Element | Convention | Example |
|---|---|---|
| Namespace | PascalCase | `Assets.Scripts.Player` |
| Class / struct / enum | PascalCase | `AttackLogic` |
| Interface | `I` + PascalCase | `IDamageable` |
| Method | PascalCase | `HandleMovement()` |
| Property | PascalCase | `CurrentHealth` |
| Event | PascalCase | `Destroyed` |
| Event handler | `On` + event | `OnDamaged()` |
| Parameter | camelCase | `damageAmount` |
| Local variable | camelCase | `movementDirection` |
| Private field | `_camelCase` | `_movementSpeed` |
| Serialized private field | `_camelCase` | `_projectileTemplate` |
| Constant | `k_PascalCase` | `k_GroundCheckDistance` |
| Static readonly field | `k_PascalCase` | `k_BaseColorId` |
| Enum value | PascalCase | `Idle`, `Chase`, `Attack` |

**Boolean** fields and properties should read naturally as questions or states.
```cs
private bool _isGrounded;
private bool _canTakeDamage;
private bool _hasTarget;
```

## Script Structure
1. Static readonly field
2. Constants
3. Serialized private fields
4. Serialized protected fields
5. Cached references
6. Private members
7. Protected members
8. Properties
9. Events
10. Unity lifecycle methods
11. Public API methods
12. Private methods
13. Protected methods

Unity lifecycle methods should follow the [Event function execution order](https://docs.unity.com/en-us/engine/6000.3/manual/scripting/managing-update-order/execution-order).  
Other methods should be alphabetically sorted.

Class members should be sorted per datatype.  
1. Unity types
2. Custom types
3. Basic types