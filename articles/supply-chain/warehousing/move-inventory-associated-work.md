---
title: Przenoszenie zapasów za pomocą skojarzonej pracy w module Zarządzanie magazynem
description: Za pomocą przesunięcia zapasów użytkownik może zdecydować, którzy pracownicy magazynu będą mogli przenosić zarezerwowane zapasy.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d996886a90037f288e839c54c8c9d932cabb21f19f2aef1552ca82b192c96a51
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736558"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a>Przenoszenie zapasów za pomocą skojarzonej pracy w module Zarządzanie magazynem

[!include [banner](../includes/banner.md)]

Za pomocą przesunięcia zapasów użytkownik może zdecydować, którzy pracownicy magazynu będą mogli przenosić zarezerwowane zapasy. Zapewnia to elastyczność w magazynach regulowanych, gdzie można zdecydować, aby nie zezwolić pracownikowi na wybieranie nowej lokalizacji pobrania dla już utworzonej pracy pobrania. Umożliwia to również kierownikowi magazynu kontrolowanie, jakie możliwości powinni mieć niektórzy mniej doświadczeni pracownicy.

Elastyczność zarządzania codziennymi operacjami pracowników magazynu może być przydatne w scenariuszach takich jak te:

## <a name="scenario-1"></a>Scenariusz 1

Firma ma stosunkowo mały obszar przyjęcia i jest on zatłoczony paletami i pudełkami oczekującymi na odłożenie. Danego dnia jest oczekiwana duża przesyłka, więc pracownik przyjmujący decyduje się na wyczyszczenie obszaru przyjęcia poprzez przeniesienie niektórych palet do pomocniczego obszaru pośredniego rozładunku.

## <a name="scenario-2"></a>Scenariusz 2

Doświadczony pracownik magazynu zauważył w magazynie możliwość skonsolidowania towarów w jednym miejscu zamiast je dzielić między trzy znajdujące się blisko siebie lokalizacje z małą ilością w każdej z nich. Pracownik chce skonsolidować ilości, przenosząc towary z każdej lokalizacji do tej samej lokalizacji i na ten sam numer identyfikacyjny.

## <a name="scenario-3"></a>Scenariusz 3

Paleta oczekuje na wysyłkę w lokalizacji pośredniej, takiej jak STAGE01, która znajduje się w pobliżu bramy dokowej BAYDOOR01. Jednak z powodu zmiany planów ciężarówka ma podjechać do bramy dokowej BAYDOOR04. Pracownik ds. spedycji wie o tym i musi się upewnić, że ciężarówka nie będzie musiała czekać na załadunek z lokalizacji STAGE01. Dlatego pracownik decyduje się przenieść towary tej wysyłki z lokalizacji STAGE01 do lokalizacji STAGE04, która znajduje się bliżej nowego miejsca docelowego.

### <a name="current-limitations"></a>Bieżące ograniczenia

Rezerwacje pracy, które można przenosić, są ograniczone do zamówienia sprzedaży, wydania zamówienia przeniesienia, przyjęcia zamówienia przeniesienia, zamówienia zakupu i pracy uzupełniania zapasów.

Przenoszenie towarów jest ograniczone w celu zapobieżenia dzieleniu wierszy pracy. Oznacza to, że jeśli masz wiersz pracy na 100 sztuk towaru A z lokalizacji Loc1, nie będzie można przenieść tylko 30 sztuk towaru A z tej lokalizacji do innej lokalizacji. To doprowadziłoby do podziału istniejącego wiersza pracy na 30 i 70 sztuk, ponieważ lokalizacje teraz są różne.

W scenariuszach z lokalizacjami pośrednimi, gdzie numer identyfikacyjny, z którego lub pod który są przesuwane towary, są ustawione jako docelowy numer identyfikacyjny dla zlecenia produkcyjnego, można przesuwać tylko całą zawartość numeru identyfikacyjnego, tak aby nie podzielić zawartości docelowego numeru identyfikacyjnego.

Obecnie są obsługiwane tylko przesunięcia ad hoc. Oznacza to, że nie będzie można przesuwać zarezerwowanych zapasów za pomocą przesunięć przy użyciu elementów menu szablonu na urządzeniu przenośnym.

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a>Ustawianie uprawnień do przesuwania zarezerwowanych zapasów dla poszczególnych pracowników

Dla pracownika, który powinien mieć możliwość przesuwania zarezerwowanych zapasów, należy zaznaczyć pole wyboru **Zezwalaj na przesuwanie zapasów za pomocą skojarzonej pracy** w obszarze **Zarządzanie magazynem \> Ustawienia \> Pracownik**.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
