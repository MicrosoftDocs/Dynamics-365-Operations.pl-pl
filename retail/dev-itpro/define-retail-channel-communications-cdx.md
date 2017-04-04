---
title: "Definiowanie komunikacji w kanale sieci sprzedaży (usługa Commerce Data Exchange)"
description: "Ten artykuł zawiera omówienie usługi Commerce Data Exchange i jej składników. Wyjaśnia on części każdego składnika odtwarzany w przekazywaniu danych między Microsoft Dynamics 365 dla operacji i kanałów sprzedaży detalicznej."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 29938d962db42a521dd8dc03b8e45e0e34410e4d
ms.openlocfilehash: d3b36ec2a3f859215d93dd7ebf1f1ecfb2731c59
ms.lasthandoff: 03/31/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Definiowanie komunikacji w kanale sieci sprzedaży (usługa Commerce Data Exchange)

Ten artykuł zawiera omówienie usługi Commerce Data Exchange i jej składników. Wyjaśnia on części każdego składnika odtwarzany w przekazywaniu danych między Microsoft Dynamics 365 dla operacji i kanałów sprzedaży detalicznej.

<a name="overview"></a>Przegląd
--------

Commerce Data Exchange to system, który przesyła dane między 365 Dynamics dla operacji i kanałów sprzedaży detalicznej, takie jak sklepy lub cegły i zaprawy sklepów. Baza danych przechowująca dane dotyczące kanału sprzedaży jest oddzielona od 365 Dynamics dla operacji bazy danych. W bazie danych kanału znajdują się tylko dane, które są wymagane dla transakcji detalicznych. Dane główne jest skonfigurowany w usłudze Dynamics 365 dla działań i rozprowadzane do kanałów. Dane transakcyjne są tworzone w punkcie sprzedaży (POS) systemu lub online przechowywania, a następnie przekazywane do 365 Dynamics dla operacji. Dystrybucja danych jest asynchroniczna. Innymi słowy proces zbierania i pakowania danych w źródle jest odrębny od procesu przyjmowania i stosowania danych w miejscu docelowym. W przypadku niektórych scenariuszy, takich jak wyszukiwanie ceny i zapasów, dane muszą być pobierane w czasie rzeczywistym. Do obsługi tych scenariuszy, usługi Commerce Data Exchange obejmuje również usługi, który umożliwia komunikację w czasie rzeczywistym pomiędzy 365 Dynamics dla operacji i kanał. 

[![Aktualizacja retail grafika](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Usługa przetwarzania asynchronicznego
Microsoft SQL Server oledzenie na 365 Dynamics dla operacji bazy danych jest używany do określenia zmian danych, które muszą być przesłane do kanałów. Zgodnie z harmonogramem dystrybucji, Dynamics 365 dla operacji pakiety danych i zapisuje go do magazynu centralnego (magazynu obiektów blob Azure). Osobny proces wsadowy korzysta z usługi Commerce Data Exchange: biblioteki Async Client, aby wstawić ten pakiet danych do bazy danych kanału. 

[![Async Service](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Transfer danych w sieci sprzedaży

Zadania harmonogramu to mechanizm dystrybuowania danych do i z lokalizacji. Zadania składają się z podzadań, które określają tabele i pola tabeli, które zawierają dane do dystrybucji. Dynamics 365 dla operacji zawiera wstępnie zdefiniowanego harmonogramu zadań i podzadań, które spełniają wymagania replikacji większości organizacji. Tworzone są następujące typy predefiniowanych zadań:

-   **Pobierz zadania** — Pobierz zadania Wyślij dane, które uległy zmianie od 365 Dynamics dla operacji do kanału baz danych. Modyfikacje rekordów są śledzone za pomocą śledzenia zmian programu SQL Server.
-   **Przesłać zadania (zadania P)** — zadania przekazywania ściągania transakcji sprzedaży z kanału do 365 Dynamics dla operacji bazy danych. Zadania P stopniowo przekazują dane. Po uruchomieniu zadnia P biblioteka klienta przetwarzania asynchronicznego sprawdza licznik replikacji dla rekordów, które już zostały odebrane z lokalizacji. Rekord jest przekazywany tylko wtedy, gdy jego licznik replikacji jest większy niż największa znaleziona wartość. Zadania P nie aktualizują danych, które zostały wcześniej przekazane.

Harmonogram dystrybucji jest używany do uruchamiania transferu danych, ręcznie lub przez planowanie zadania wsadowego w usłudze Dynamics 365 dla operacji. Harmonogram dystrybucji może zawierać jedną lub więcej grup danych kanału i co najmniej jedno zadanie harmonogramu.

## <a name="realtime-service"></a>Usługi czasu rzeczywistego
Commerce Data Exchange: Real-time Service jest to zintegrowana usługa, która zapewnia komunikację w czasie rzeczywistym między 365 Dynamics dla operacji i kanałów sprzedaży detalicznej. Real-time Service umożliwia poszczególne komputery POS i sklepów internetowych do pobierania określonych danych z systemu Dynamics 365 dla operacji w czasie rzeczywistym. Chociaż większość kluczowych operacji mogą być wykonywane w bazie danych kanałów lokalnych, następujące scenariusze wymagają bezpośredniego dostępu do danych przechowywanych w usłudze Dynamics 365 dla operacji:

-   Wydawanie i realizacja kart upominkowych.
-   Realizowanie punktów lojalnościowych.
-   Wydawanie i realizowanie faktur korygujących.
-   Tworzenie lub aktualizowanie rekordów odbiorcy.
-   Tworzenie, aktualizowanie i kończenie zamówienia sprzedaży.
-   Przyjmowanie na magazyn według zamówienia zakupu lub zamówienia przeniesienia.
-   Zliczanie stanu zapasów.
-   Pobieranie transakcji sprzedaży w sklepach oraz zamykanie transakcji dotyczących zwrotów.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Tworzony jest wstępnie zdefiniowany profil usługi Real-time Service.


