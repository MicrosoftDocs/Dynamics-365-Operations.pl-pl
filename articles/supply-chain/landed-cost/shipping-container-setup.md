---
title: Kontenery wysyłkowe
description: W tym temacie opisano, jak skonfigurować informacje o kontenerach wysyłkowych dla modułu Koszt z wyładunkiem.
author: sherry-zheng
manager: tfehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ca712aa7f07792861d5ba36afd8d7b63cc9ce8fb
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500965"
---
# <a name="shipping-container-setup"></a>Konfiguracja kontenera wysyłkowego

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano, jak skonfigurować informacje o kontenerach wysyłkowych dla modułu **Koszt z wyładunkiem**.

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a>Konfigurowanie typów kontenerów wysyłkowych

Typy kontenerów wysyłkowych określają typy kontenerów wysyłkowych, które są dostępne do użycia podczas wysyłki i podróży.

Aby pracować z typami kontenerów wysyłkowych, przejdź do **Koszt z wyładunkiem \> Konfiguracja kontenera \> Typy kontenerów wysyłkowych**. Można tam wyświetlać, dodawać i usuwać rekordy typów kontenerów. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Typ kontenera wysyłkowego | Wprowadź unikalną nazwę/numer identyfikacyjny typu kontenera. |
| opis | Wprowadź opis typu kontenera wysyłkowego. |
| Objętość | Wprowadź maksymalną objętość dozwoloną w kontenerach transportowych tego typu. |
| Masa | Wprowadź maksymalną wagę dozwoloną w kontenerach transportowych tego typu. |
| Z możliwością zwrotu | Określ, czy kontenery transportowe tego typu mogą zostać zwrócone dostawcy po ich wykorzystaniu podczas podróży. Jeśli ta opcja ma wartość *Tak*, w przypadku zwrotu kontenerów wysyłkowych tego typu do portu pochodzenia mogą być stosowane dodatkowe koszty. |

## <a name="set-up-shipping-containers"></a>Konfigurowanie kontenerów przewozowych

Rekordów kontenerów wysyłkowych można używać do identyfikowania każdego kontenera podczas podróży. Tworząc podróż, możesz wybrać dla niej określony kontener z listy wszystkich zapisów kontenerów wysyłkowych, które zdefiniowałeś w tym miejscu. Ta funkcja jest szczególnie przydatna, jeśli firma posiada własne kontenery wysyłkowe.

Nie trzeba wprowadzać numerów kontenerów wysyłkowych dla kontenerów wysyłkowych, które będą używane tylko jeden raz. Zamiast tego można dodać numer kontenera wysyłkowego podczas tworzenia podróży.

Rekordy kontenerów wysyłkowych są używane tylko w rekordzie Koszt z wyładunkiem. Nie są one dostępne w standardowym module **Zarządzania transportem** (TMS).

Aby pracować z kontenerami wysyłkowymi, przejdź do **Koszt z wyładunkiem \> Konfiguracja kontenera \> Kontenery wysyłkowe**. Możesz tam przeglądać, dodawać i usuwać zapisy swoich kontenerów transportowych. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Kontener wysyłkowy | Wprowadź unikalną nazwę/numer identyfikacyjny kontenera. |
| Typ kontenera wysyłkowego | Wybierz typ kontenera wysyłkowego. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie typów kontenerów wysyłkowych](#shipping-container-types) we wcześniejszej części tego tematu. |

> [!NOTE]
> - Konfiguracja kontenera wysyłkowego jest opcjonalna. Zwykle będziesz go używać tylko wtedy, gdy Twoja firma posiada własne kontenery transportowe lub często ponownie wykorzystuje te same kontenery transportowe.
> - Nie obliczono cyfr kontrolnych dla numerów kontenerów wysyłkowych.

## <a name="set-up-unit-types"></a><a name="unit-types"></a>Skonfiguruj typy jednostek

Typy jednostek określają dodatkowe grupy i metody identyfikacji kontenerów transportowych. Typ jednostki jest zwykle używany do identyfikacji rodzaju kontenera, w którym pakowane są towary, takiego jak palety lub beczki. Typ jednostki można wybrać podczas konfigurowanie kontenera na stronie **Wszystkie kontenery wysyłkowe**.

Typy jednostek są używane tylko w kosztach z wyładunkiem. Nie są dostępne w TMS.

Aby pracować z typami jednostek, przejdź do **Koszt z wyładunkiem \> Konfiguracja kontenera \> Typy jednostek**. Można tam wyświetlać, dodawać i usuwać rekordy typów jednostek. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Typ jednostki | Wprowadź unikalną nazwę/numer identyfikacyjny typu jednostek. |
| opis | Umożliwia wprowadzenie opisu typu jednostki. |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a>Skonfiguruj typy chłodnictwa

Typy chłodzenia określają dodatkowe grupy i metody identyfikacji kontenerów wysyłkowych (zwykle kontenerów chłodniczych). Typ chłodzenia można wybrać podczas konfigurowanie kontenera na stronie **Wszystkie kontenery wysyłkowe**.

Aby pracować z typami chłodzenia, przejdź do **Koszt z wyładunkiem \> Konfiguracja kontenera \> Typy chłodzenia**. Można tam wyświetlać, dodawać i usuwać rekordy typów chłodzenia. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Typ systemu chłodzenia | Wprowadź unikalną nazwę/numer identyfikacyjny typu chłodzenia. |
| opis | Wprowadź opis typu chłodzenia. |
