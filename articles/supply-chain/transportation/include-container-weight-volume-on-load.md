---
title: Uwzględnianie wagi i objętości kontenera w ładunku
description: W tym temacie opisano jak skonfigurować i zastosować funkcje w celu dodania wagę i objętość kontenera do ładunków.
author: Henrikan
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9196e9c4ce1a8aa629400b8bf379e7164a797b85
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102646"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]