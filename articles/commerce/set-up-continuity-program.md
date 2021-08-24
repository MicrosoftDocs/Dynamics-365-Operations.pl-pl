---
title: Konfigurowanie programów sprzedaży ciągłej dla biur obsługi
description: W tym artykule opisano sposób konfigurowania programu sprzedaży ciągłej dla biura obsługi.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 39c3e6d740bff2af27a2fba2ac4c406c01b43a87218fdc1dcfe094c147cd3de3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716157"
---
# <a name="set-up-continuity-programs-for-call-centers"></a>Konfigurowanie programów sprzedaży ciągłej dla biur obsługi

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób konfigurowania programu sprzedaży ciągłej dla biura obsługi.

W programie ciągłości nazywanym także programem cyklicznych zamówień, klienci otrzymują regularne wysyłki produktów według wstępnie zdefiniowanego harmonogramu. Każda wysyłka może zawierać inny produkt, tak jak w przypadku klubu książki miesiąca, lub ten sam produkt, który jest wysyłany wielokrotnie. Aby skonfigurować program sprzedaży ciągłej, należy wykonać następujące zadania.

1. Ustaw parametry ciągłości na stronie **Parametry biura obsługi**.
2. Utwórz program sprzedaży ciągłej, który określa szczegóły, takie jak harmonogram płatności, czas wysyłki, oraz czy fakturowanie dokonywane jest na początku. Należy także dodać listę produktów, które są uwzględniane w programie sprzedaży ciągłej. Każdy produkt otrzymuje numer identyfikacyjny zdarzenia przypisany kolejno, począwszy od 1. Identyfikatory zdarzeń określają kolejność, w której produkty są wysyłane.

    - Klienci otrzymują inny produkt w każdej wysyłce, produkty są wysyłane w kolejności według ich identyfikatorów zdarzeń, począwszy od bieżącego zdarzenia.
    - Kiedy klienci otrzymują ten sam produkt w każdej wysyłce, lista zawiera tylko jeden produkt, który zawiera jeden identyfikator zdarzenia. To samo zdarzenie powtarza się. Można określić, ile razy każde zdarzenie ma być powtórzone.

3. Utwórz produkt nadrzędny, który reprezentuje program ciągłości sprzedaży utworzony w zadaniu 2. Po dodaniu tego produktu do zamówienia sprzedaży otworzy się okno **Ciągłość**. Tej strony można następnie użyć do tworzenia rzeczywistego zamówienia sprzedaży ciągłej. Produkt nadrzędny nie określa poszczególnych produktów, które użytkownik otrzymuje w każdej wysyłce.

Po skonfigurowaniu programu ciągłości zgodnie z opisem powyżej można utworzyć zamówienie ciągłe dla odbiorcy. Również wystąpić konieczność wykonania następujących dodatkowych zadań konserwacyjnych.

- **Aktualizuj okres bieżącego zdarzenia ciągłości** — skonfiguruj zadanie wsadowe, które informuje system, jaki jest okres bieżącego zdarzenia.
- **Utwórz podrzędne zamówienia ciągłej sprzedaży** — utwórz podrzędne zamówienia z nadrzędnego zamówienia ciągłej sprzedaży.
- **Płatności w procesie sprzedaży ciągłej** — rozliczenia i powiadomienia przetwarzania dla płatności, które są skojarzone z zamówieniami sprzedaży ciągłej.
- **Rozszerzanie wierszy sprzedaży ciągłej** (jeśli wymagane) — rozszerzenie liczby przypadków, w których można powtarzać zdarzenia. Powtarzanie wysyłek można następnie powiększyć poza limit, który został ustawiony w polu **Próg powtarzania zdarzenia ciągłości pracy** w parametrach biura obsługi.
- **Dokonaj aktualizacji ciągłości** (jeśli wymagane) — synchronizuj zmiany między program ciągłości i nadrzędnymi zamówieniami sprzedaży ciągłej.
- **Zamknij wiersze i zamówienia nadrzędne ciągłe** — zamknij zamówienia ciągłe.


[!INCLUDE[footer-include](../includes/footer-banner.md)]