---
title: "Dodawanie lokalizacji i typów relacji stron"
description: "W tym temacie opisano, jak dodać nową lokalizację i typ relacji stron."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8435389a523d8393e9d4daa0cb1244203c0dbb12
ms.openlocfilehash: bd8c5a18d69e1952d32675d759b8b2a997844822
ms.contentlocale: pl-pl
ms.lasthandoff: 05/21/2018

---

# <a name="add-new-location-roles-and-party-relationship-types"></a>Dodawanie nowych ról w lokalizacji i typów relacji stron 

## <a name="add-new-location-roles"></a>Dodawanie nowych ról w lokalizacji

Istnieją dwa sposoby dodawania nowych ról lokalizacji dla adresu i informacji kontaktowych:

-  Dodanie za pośrednictwem strony **Cel informacji o adresie i osobie kontaktowej**. Nowa rola zostanie zapisana w tabeli **LogisticsLocationRole** z parametrem type = 0, co oznacza, że rola nie jest rolą systemową zdefiniowaną w wyliczeniu **LogisticsLocationRoleType** i jego rozszerzeniach. Użytkownik będzie mógł używać tej roli podczas tworzenia informacji adresowych lub kontaktowych.

    ![Przeznaczenie informacji o adresie i zawartości](media/Address-Contact.PNG)

-  Dodanie do rozszerzenia elementu stałotekstowego **LogisticsLocationRoleType**, a następnie rozpowszechnienie za pomocą procesu synchronizacji bazy danych.

    1.  Utwórz rozszerzenie do elementu stałotekstowego **LogisticsLocationRoleType** i dodaj nową rolę w rozszerzeniu. 
  
        ![LogisticsLocationRoleType](media/Logistics.PNG)

    2. Utwórz nowy plik zasobów dla nowej roli, a następnie przypisz wartość do jego właściwości.
     
     ![Nowy plik zasobów](media/Resource.PNG)
        
    3.  Utwórz klasę wypełniania danymi i określ metodę programu obsługi w celu wypełnienia nowej roli. 

        ![Wypełnianie danymi](media/Dirdata.PNG)

    4.  Aby przeprowadzić test wypełniania nowej roli lokalizacji, można utworzyć klasę wykonywalną i wywołać DirDataPopulation::insertLogisticsLocationRoles() w Main(). Po zakończeniu tego procesu nowa rola powinna być widoczna w tabeli **LogisticsLocationRole** z typem \> 0. Nowa rola będzie wyświetlana na stronie **Cel informacji o adresie i osobie kontaktowej**.

        ![Wstawianie nowej lokalizacji](media/InsertNewLocation.PNG)

## <a name="add-new-party-relationship-types"></a>Dodawanie nowych typów relacji stron 

Istnieją dwa sposoby dodawania nowego typu relacji:

-   Dodanie za pośrednictwem strony **Typy relacji**. Nowa relacja zostanie zapisana w tabeli **DirRelationshipTypeTable** z parametem systemtype = 0.

    ![Typy relacji](media/Relationship.PNG)

-  Dodanie do rozszerzenia elementu stałotekstowego **DirSystemRelationshipType**, a następnie rozpowszechnienie za pomocą procesu synchronizacji bazy danych.

    1.  Utwórz rozszerzenie w elemencie stałotekstowym **DirSystemRelationshipType** i dodaj nowy typ relacji.

    2. Utwórz inicjatora dla tego nowego typu. Kilka przykładów można znaleźć w kodzie podstawowym. Jeden z nich to  **DirRelationshipTypeChildInitialize**. Jest to klasa inicjatora dla typu relacji strony „Obiekt podrzędny”. Można zacząć od inicjatora poprzez skopiowanie i wklejenie tego kodu, a następnie zaktualizowanie wyróżnionych obszarów.
    
    ![DirRelationshipChild](media/DirRelationship.PNG)

    3.  Aby przeprowadzić test wypełniania nowego typu relacji, można utworzyć klasę wykonywalną i wywołać DirDataPopulation::insertDirRelationshipTypes() w Main(). Powinien zostać wyświetlony nowy typ relacji w **DirRelationshipTypeTable**. Będzie on widoczny na stronie **Typy relacji**.

        ![Klasa możliwa do uruchomienia](media/Runnable.PNG)

