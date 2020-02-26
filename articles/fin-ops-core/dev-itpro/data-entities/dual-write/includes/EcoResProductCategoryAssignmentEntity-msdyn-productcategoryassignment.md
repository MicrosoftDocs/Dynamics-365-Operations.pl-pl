## <a name="product-category-assignments-to-msdyn_productcategoryassignments"></a>Przypisania kategorii produktów do msdyn_productcategoryassignments

Ten szablon synchronizuje dane między aplikacjami Finance and Operations i usługami Common Data Service.

Pole aplikacji Finance and Operations | Typ mapy | Inne pole rozwiązania Dynamics 365 | Wartość domyślna
---|---|---|---
PRODUCTNUMBER | = | msdyn_globalproduct.msdyn_productnumber | 
PRODUCTCATEGORYNAME | = | msdyn_productcategory.msdyn_name | 
PRODUCTCATEGORYHIERARCHYNAME | = | msdyn_productcategory.msdyn_hierarchy.msdyn_name | 
PRODUCTNUMBER | >> | msdyn_name | 
