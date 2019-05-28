---
title: Uwzględnianie wagi i objętości kontenera w ładunku
description: W tym temacie opisano jak skonfigurować i zastosować funkcje w celu dodania wagę i objętość kontenera do ładunków.
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adbaa379889d373d597b2f6882b78f82bd71ae57
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549228"
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
