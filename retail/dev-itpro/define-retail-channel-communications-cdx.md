---
title: "Definiowanie komunikacji w kanale sieci sprzedaży (usługa Commerce Data Exchange)"
description: "Ten artykuł zawiera omówienie usługi Commerce Data Exchange i jej składników. Objaśniono rolę każdego składnika w przesyłaniu danych między programem Microsoft Dynamics 365 for Operations a kanałami sprzedaży detalicznej."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
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

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie usługi Commerce Data Exchange i jej składników. Objaśniono rolę każdego składnika w przesyłaniu danych między programem Microsoft Dynamics 365 for Operations a kanałami sprzedaży detalicznej.

<a name="overview"></a>Przegląd
--------

Commerce Data Exchange to system, który przesyła dane między programem Dynamics 365 for Operations a kanałami sieci sprzedaży, np. między sklepami internetowymi i tradycyjnymi. Baza danych, która przechowuje dane dla kanału sprzedaży, różni się od bazy danych programu Dynamics 365 for Operations. W bazie danych kanału znajdują się tylko dane, które są wymagane dla transakcji detalicznych. Dane główne są skonfigurowane w programie Dynamics 365 for Operations i dystrybuowane do kanałów. Dane transakcyjne są tworzone w punkcie sprzedaży (POS) lub sklepie internetowym, a następnie przekazywane do programu Dynamics 365 for Operations. Dystrybucja danych jest asynchroniczna. Innymi słowy proces zbierania i pakowania danych w źródle jest odrębny od procesu przyjmowania i stosowania danych w miejscu docelowym. W przypadku niektórych scenariuszy, takich jak wyszukiwanie ceny i zapasów, dane muszą być pobierane w czasie rzeczywistym. Na potrzeby obsługi tych scenariuszy usługi Commerce Data Exchange obejmują także usługę umożliwiającą komunikację w czasie rzeczywistym między programem Dynamics 365 for Operations a kanałem. 

[![updated-retail-graphic](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Usługa przetwarzania asynchronicznego
Funkcja śledzenia zmian zawarta w programie Microsoft SQL Server, która działa w bazie danych programu Dynamics 365 for Operations, służy do określania zmian danych, które muszą zostać wysłane do kanałów. Zgodnie z harmonogramem dystrybucji program Dynamics 365 for Operations pakuje te dane i zapisuje w centralnym magazynie (magazynie obiektów blob Azure). Osobny proces wsadowy korzysta z usługi Commerce Data Exchange: biblioteki Async Client, aby wstawić ten pakiet danych do bazy danych kanału. 

[![Usługa przetwarzania asynchronicznego](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Transfer danych w sieci sprzedaży

Zadania harmonogramu to mechanizm dystrybuowania danych do i z lokalizacji. Zadania składają się z podzadań, które określają tabele i pola tabeli, które zawierają dane do dystrybucji. Dynamics 365 for Operations zawiera wstępnie zdefiniowany harmonogram zadań i podzadań, które spełniają wymagania replikacji w większości organizacji. Tworzone są następujące typy predefiniowanych zadań:

-   **Zadania pobierania** — Zadania pobierania wysyłają dane, które zostały zmienione, z programu Dynamics 365 for Operations do bazy danych kanału. Modyfikacje rekordów są śledzone za pomocą śledzenia zmian programu SQL Server.
-   **Zadania przekazywania (zadania P)** — Zadania przekazywanie ściągają transakcje sprzedaży z kanału do bazy danych programu Dynamics 365 for Operations. Zadania P stopniowo przekazują dane. Po uruchomieniu zadnia P biblioteka klienta przetwarzania asynchronicznego sprawdza licznik replikacji dla rekordów, które już zostały odebrane z lokalizacji. Rekord jest przekazywany tylko wtedy, gdy jego licznik replikacji jest większy niż największa znaleziona wartość. Zadania P nie aktualizują danych, które zostały wcześniej przekazane.

Harmonogram dystrybucji jest używany do uruchamiania transferu danych, ręcznie lub poprzez zaplanowanie zadania wsadowego w programie Dynamics 365 for Operations. Harmonogram dystrybucji może zawierać jedną lub więcej grup danych kanału i co najmniej jedno zadanie harmonogramu.

## <a name="realtime-service"></a>Usługa Real-time Service
Commerce Data Exchange: Real-time Service to zintegrowana usługa zapewniająca synchroniczną komunikację w czasie rzeczywistym między programem Dynamics 365 for Operations a kanałami sprzedaży detalicznej. Usługi Real-time Service umożliwiają poszczególnym komputerom punktu sprzedaży i sklepów internetowych pobieranie określonych danych z programu Dynamics 365 for Operations w czasie rzeczywistym. Chociaż większość kluczowych operacji może być wykonywana w lokalnej bazie danych kanału, następujące scenariusze wymagają bezpośredniego dostępu do danych przechowywanych w programie Dynamics 365 for Operations:

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




