---
title: "Definiowanie komunikacji w kanale sieci sprzedaży (usługa Commerce Data Exchange)"
description: "Ten artykuł zawiera omówienie usługi Commerce Data Exchange i jej składników. Objaśniono rolę każdego składnika w przesyłaniu danych między programem Microsoft Dynamics 365 for Retail a kanałami sprzedaży detalicznej."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 68252e52da47b89166627edbf2aa530e762354c6
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# Definiowanie komunikacji w kanale sieci sprzedaży (usługa Commerce Data Exchange)
<a id="define-retail-channel-communications-commerce-data-exchange" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie usługi Commerce Data Exchange i jej składników. Objaśniono rolę każdego składnika w przesyłaniu danych między programem Microsoft Dynamics 365 for Retail a kanałami sprzedaży detalicznej.

Przegląd
<a id="overview" class="xliff"></a>
--------

Commerce Data Exchange to system, który przesyła dane między programem Dynamics 365 for Retail a kanałami sieci sprzedaży, np. między sklepami internetowymi i tradycyjnymi. Baza danych, która przechowuje dane dla kanału sprzedaży, różni się od bazy danych programu Dynamics 365 for Retail. W bazie danych kanału znajdują się tylko dane, które są wymagane dla transakcji detalicznych. Dane główne są skonfigurowane w programie Dynamics 365 for Retail i dystrybuowane do kanałów. Dane transakcyjne są tworzone w punkcie sprzedaży (POS) lub sklepie internetowym, a następnie przekazywane do programu Dynamics 365 for Retail. Dystrybucja danych jest asynchroniczna. Innymi słowy proces zbierania i pakowania danych w źródle jest odrębny od procesu przyjmowania i stosowania danych w miejscu docelowym. W przypadku niektórych scenariuszy, takich jak wyszukiwanie ceny i zapasów, dane muszą być pobierane w czasie rzeczywistym. Na potrzeby obsługi tych scenariuszy usługi Commerce Data Exchange obejmują także usługę umożliwiającą komunikację w czasie rzeczywistym między programem Dynamics 365 for Retail a kanałem. 

[![updated-retail-graphic](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## Usługa przetwarzania asynchronicznego
<a id="async-service" class="xliff"></a>
Funkcja śledzenia zmian zawarta w programie Microsoft SQL Server, która działa w bazie danych programu Dynamics 365 for Retail, służy do określania zmian danych, które muszą zostać wysłane do kanałów. Zgodnie z harmonogramem dystrybucji program Dynamics 365 for Retail pakuje te dane i zapisuje w centralnym magazynie (magazynie obiektów blob Azure). Osobny proces wsadowy korzysta z usługi Commerce Data Exchange: biblioteki Async Client, aby wstawić ten pakiet danych do bazy danych kanału. 

[![Usługa przetwarzania asynchronicznego](./media/async-300x239.png)](./media/async.png)

### Transfer danych w sieci sprzedaży
<a id="retail-scheduler" class="xliff"></a>

Zadania harmonogramu to mechanizm dystrybuowania danych do i z lokalizacji. Zadania składają się z podzadań, które określają tabele i pola tabeli, które zawierają dane do dystrybucji. Dynamics 365 for Retail zawiera wstępnie zdefiniowany harmonogram zadań i podzadań, które spełniają wymagania replikacji w większości organizacji. Tworzone są następujące typy predefiniowanych zadań:

-   **Zadania pobierania** — Zadania pobierania wysyłają dane, które zostały zmienione, z programu Dynamics 365 for Retail do bazy danych kanału. Modyfikacje rekordów są śledzone za pomocą śledzenia zmian programu SQL Server.
-   **Zadania przekazywania (zadania P)** — Zadania przekazywanie ściągają transakcje sprzedaży z kanału do bazy danych programu Dynamics 365 for Retail. Zadania P stopniowo przekazują dane. Po uruchomieniu zadnia P biblioteka klienta przetwarzania asynchronicznego sprawdza licznik replikacji dla rekordów, które już zostały odebrane z lokalizacji. Rekord jest przekazywany tylko wtedy, gdy jego licznik replikacji jest większy niż największa znaleziona wartość. Zadania P nie aktualizują danych, które zostały wcześniej przekazane.

Harmonogram dystrybucji jest używany do uruchamiania transferu danych, ręcznie lub poprzez zaplanowanie zadania wsadowego w programie Dynamics 365 for Retail. Harmonogram dystrybucji może zawierać jedną lub więcej grup danych kanału i co najmniej jedno zadanie harmonogramu.

## Usługa Real-time Service
<a id="realtime-service" class="xliff"></a>
Commerce Data Exchange: Real-time Service to zintegrowana usługa zapewniająca synchroniczną komunikację w czasie rzeczywistym między programem Dynamics 365 for Retail a kanałami sprzedaży detalicznej. Usługi Real-time Service umożliwiają poszczególnym komputerom punktu sprzedaży i sklepów internetowych pobieranie określonych danych z programu Dynamics 365 for Retail w czasie rzeczywistym. Chociaż większość kluczowych operacji może być wykonywana w lokalnej bazie danych kanału, następujące scenariusze wymagają bezpośredniego dostępu do danych przechowywanych w programie Dynamics 365 for Retail:

-   Wydawanie i realizacja kart upominkowych.
-   Realizowanie punktów lojalnościowych.
-   Wydawanie i realizowanie faktur korygujących.
-   Tworzenie lub aktualizowanie rekordów odbiorcy.
-   Tworzenie, aktualizowanie i kończenie zamówienia sprzedaży.
-   Przyjmowanie na magazyn według zamówienia zakupu lub zamówienia przeniesienia.
-   Zliczanie stanu zapasów.
-   Pobieranie transakcji sprzedaży w sklepach oraz zamykanie transakcji dotyczących zwrotów.

[![Usługa Real-time Service](./media/rts.png)](./media/rts.png) 

Tworzony jest wstępnie zdefiniowany profil usługi Real-time Service.




