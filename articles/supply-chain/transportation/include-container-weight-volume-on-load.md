---
title: "Uwzględnianie wagi i objętości kontenera w ładunku"
description: "W tym temacie opisano jak skonfigurować i zastosować funkcje w celu dodania wagę i objętość kontenera do ładunków."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4190b5cb05cccc3d762d8ad153ecbd467fa0a332
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="include-container-weight-and-volume-on-load"></a>Uwzględnianie wagi i objętości kontenera w ładunku

[!include [banner](../includes/banner.md)]

Funkcja dodawania wagi i objętości do ładunku umożliwia uzyskanie przejrzystych informacji o całkowitej wadze i objętości kontenerów i towarów zawartych w ładunku.

Ładunek zawiera jedną lub wiele wysyłek, a te wysyłki mogą zawierać osobne towary należące do jednego lub kilku zamówień sprzedaży. Towary są przechowywane w kontenerze, a kontenery ładowane w ramach ładunku. Towary poza kontenerem także mogą być częścią ładunku. Na podstawie tych warunków system oblicza wartości wagi i objętości ładunku, uwzględniając wagę i objętość kontenerów oraz towarów.

Jeżeli obliczone wartości są niedokładne, można je dostosować wprowadzając rzeczywiste wartości wagi i objętości ładunku. Te wartości wagi i objętości są używane w procesach zarządzania transportem. Wartości są na przykład używane w pulpicie ustalania stawek i wyznaczania tras, gdzie ułatwiają zdefiniowanie stawki i trasy ładunków i są także używane dla metod płatności za transport i ewidencjonowanie kierowców.

## <a name="where-it-applies"></a>Zastosowanie

Funkcja uwzględniania wagi i objętości kontenera w ładunku ma zastosowanie w procesach zarządzania transportem, takich jak pulpit ustalania stawek i wyznaczania tras, metody płatności za transport i ewidencjonowanie kierowców.

## <a name="how-it-is-set-up"></a>Sposób konfiguracji

Liczba kontenerów, którą należy uwzględnić dla ładunku jest obliczana na podstawie wagi i objętości kontenera i procentu wykorzystania kontenera.

-   Aby ustawić wagę i objętość dla kontenera kliknij kolejno opcje **Zarządzanie magazynem** \> **Konfiguracja** \> **Kontenery** \> **Typy kontenerów**.

-   Aby ustawić procent wykorzystania kontenerów, kliknij kolejno opcje **Zarządzanie magazynem** \> **Konfiguracja** \> **Kontenery** \> **Grupy kontenerów**, a następnie wprowadź wartość w polu **Procent wykorzystania kontenera**.

