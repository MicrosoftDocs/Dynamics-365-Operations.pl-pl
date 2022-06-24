---
title: Synchronizacja kodów dyspozycji
description: W tym artykule wyjaśniono synchronizację kodów dyspozycji dla handlu międzyfirmowego
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: d347181dd6ba12de0e114d74d43cd46230ba4fb7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905668"
---
# <a name="synchronize-intercompany-disposition-codes"></a>Synchronizacja międzyfirmowych kodów dyspozycji

[!include [banner](../../includes/banner.md)]

Aby obsługiwać zwroty międzyfirmowe, Microsoft Dynamics 365 Supply Chain Management umożliwia mapowanie zewnętrznie zdefiniowanych kodów dyspozycji na odpowiadające im wewnętrzne kody dyspozycji. Gdy tworzony jest łańcuch międzyfirmowy, akcje dyspozycji w dwóch zmapowanych do siebie firmach muszą być takie same. Jeśli się różnią, proces synchronizacji zakończy się niepowodzeniem.

## <a name="about-disposition-codes-for-three-legged-direct-returns"></a>Informacje o kodach dyspozycji dla trójetapowych zwrotów bezpośrednich

Kody dyspozycji są synchronizowane z wiersza międzyfirmowego zamówienia sprzedaży do oryginalnego wiersza zamówienia sprzedaży. Synchronizacja ma jednak tylko jeden natychmiastowy wpływ na wiersz oryginalnego zamówienia sprzedaży. Ten efekt polega na tym, że opłaty za wiersze różne są usuwane na podstawie kodu dyspozycji i opłaty dodatkowej skonfigurowanej w firmie A. Firma A to firma, która tworzy zamówienie zwrotu.

W trójetapowym łańcuchu dostaw bezpośrednich wszystkie akcje dyspozycji są obsługiwane w wierszu międzyfirmowego zamówienia sprzedaży. Jeśli jednak produkt jest zwracany do klienta, należy potwierdzić, że adres dostawy w zamówieniu zwrotu jest zgodny z adresem dostawy klienta podanym w pierwotnym zamówieniu.

> [!NOTE]
> Nie istnieją kody dyspozycji dla zamówień zakupu. W związku z tym synchronizacja kodów dyspozycji z międzyfirmowego zamówienia sprzedaży do oryginalnego zamówienia zwrotu musi być wykonywana od zamówienia sprzedaży do zamówienia sprzedaży.

## <a name="replacing-returned-items"></a>Zastępowanie zwróconych towarów

Jeśli zwrócony towar jest zastępowany, a zamówienie wymiany zostało już utworzone w firmie B, nie można wybrać kodu dyspozycji i nie jest tworzone żadne dodatkowe zamówienie wymiany w firmie A.

## <a name="rules-for-intercompany-direct-deliveries"></a>Zasady dostaw bezpośrednich międzyfirmowych

Następujące ogólne zasady mają zastosowanie do pierwotnych zamówień zwrotu w scenariuszach, które obejmują międzyfirmowe dostawy bezpośrednie:

- Jeśli bazowa akcja dyspozycji w wierszu oryginalnego zamówienia sprzedaży to Kredyt i złom, Kredyt lub Zwrot do klienta, stosowana jest akcja dyspozycji kredytu. Jednak kod akcji Zwrot do odbiorcy ustawia kwotę netto na 0 (zero) w istniejącym wierszu i w nowo zsynchronizowanym wierszu z międzyfirmowego zamówienia sprzedaży. Ponadto wiersze odpadków nigdy nie są synchronizowane. Po dodaniu wiersza do międzyfirmowego zamówienia sprzedaży nie jest on nigdy synchronizowany w przypadku zamówienia sprzedaży, które ma dodatnią ilość i akcję dyspozycji Likwidacji (na przykład Uznanie i likwidacja lub Zamiana i likwidacja).
- Podstawowe działanie dyspozycji Kredyt i zastąp lub Zlikwiduj i zastąp nie jest unieważniane. Jest on traktowany jako działanie związane z rozdysponowaniem w ramach operacji Kredyt i wymiana" lub Zlikwiduj i zastąp. Zasada ta obowiązuje nawet wtedy, gdy w firmie A nie zostanie utworzona linia do złomowania, a w firmie B (firmie, która otrzymała zwrócony element) nie zostanie utworzone zamówienie na wymianę. Zamówienie zastępcze jest tworzone w firmie A tylko wtedy, gdy wykonywana jest aktualizacja dowodu pakowania.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
