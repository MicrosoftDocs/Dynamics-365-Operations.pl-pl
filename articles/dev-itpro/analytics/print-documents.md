---
title: "Drukowanie w aplikacjach rozwiązania Finance and Operations"
description: "W programie Microsoft Dynamics 365 for Finance and Operations dokumenty można drukować przy użyciu drukarki lokalnej lub urządzenia podłączonego do sieci. Ten artykuł zawiera omówienie sposobu drukowania dokumentów."
author: TJVass
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: IT Pro, Application User
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.custom: 69161
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 30a418e6c49849369f0a0e3ffa28f31b9b88b7e7
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="printing-in-finance-and-operations-applications"></a>Drukowanie w aplikacjach rozwiązania Finance and Operations

[!INCLUDE [banner](../includes/banner.md)]

W programie Microsoft Dynamics 365 for Finance and Operations dokumenty można drukować przy użyciu drukarki lokalnej lub urządzenia podłączonego do sieci. Ten artykuł zawiera omówienie sposobu drukowania dokumentów.

<a name="printing-overview"></a>Ogólne informacje o drukowaniu
-----------------

Program Microsoft Dynamics 365 for Finance and Operations zawiera zintegrowane usługi i aplikacje klienckie, które pozwalają łatwo generować, przechowywać i rozpowszechniać dokumenty wspierające działalność biznesową. W programie Finance and Operations dokumenty można drukować przy użyciu drukarki lokalnej lub urządzenia podłączonego do sieci. Ponadto strony i raporty programu Finance and Operations można eksportować bezpośrednio z klienta jako pliki PDF lub dokumenty programu Microsoft Office. Funkcja rozproszonego obciążenia pracą pozwala drukować dokumenty biznesowe bezpośrednio z urządzenia przenośnego przy użyciu zasobów sieciowych. Wymagania dotyczące drukowania mogą się różnić, jednak zwykle we wszystkich branżach trzeba tworzyć drukowane kopie dokumentów biznesowych przy użyciu programu Finance and Operations. Drukowanie dokumentów na urządzeniach sieciowych z hostowanych aplikacji stwarza unikatowe wyzwania. Oto kilka przykładów:

-   Sterowniki druku mogą być niedostępne na urządzeniu użytkownika.
-   Urządzenie użytkownika może nie być podłączone do firmowej sieci.

Używając dedykowanego hosta i wykonując kilka prostych kroków, administratorzy systemu mogą tak skonfigurować wdrożenia, aby użytkownicy mogli drukować bezpośrednio z aplikacji biznesowych na urządzeniach sieciowych.

### <a name="printing-scenarios-in-finance-and-operations-applications"></a>Scenariusze drukowania w aplikacjach rozwiązania Finance and Operations

W poniższej tabeli opisano trzy podstawowe scenariusze drukowania w aplikacjach rozwiązania Finance and Operations.

| Scenariusz                        | Cel                                                      | Rozwiązanie                                                                                                            |
|---------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| 1. Drukowanie tego, co widać        | Drukowanie zawartości obecnie wyświetlanej w przeglądarce.             | Dla przeglądarki jest generowana wersja strony sieci Web specjalnie przystosowana do druku.                                             |
| 2. Interaktywne drukowanie         | Drukowanie precyzyjnie zdefiniowanego dokumentu na lokalnie podłączonym urządzeniu. | Można wyeksportować wersję PDF raportu i pobrać ją do przeglądarki.                                          |
| 3. Drukowanie na urządzeniu sieciowym | Wysyłanie precyzyjnie zdefiniowanego dokumentu do drukarki w domenie.     | Precyzyjnie zdefiniowany dokument jest wysyłany do aplikacji klienckiej, która jest uruchomiona na serwerze umieszczonym w domenie odbiorcy. |

Ponieważ stosowane rozwiązanie różni się w zależności od scenariusza, aplikacje rozwiązania Finance and Operations zawierają wbudowane usługi i narzędzia pomagające użytkownikom osiągnąć wyznaczone cele:

-   **Scenariusz 1** jest obsługiwany przez renderowanie w przeglądarce zawartości z klienta obsługującego format HTML5.
-   **Scenariusz 2** korzysta z aplikacji klienckich i usługi Microsoft Office 365.
-   **Scenariusz 3** wymaga obsługi ze strony aplikacji klienckich oraz usług hostowanych na platformie Microsoft Azure.

Oprócz platformy wdrożonej w ramach subskrypcji usługi Azure odbiorcy mogą korzystać z aplikacji rozwiązania Finance and Operations, które są zintegrowane z platformą Azure i pochodzą od jej producenta, co ułatwia korzystanie z urządzeń w domenie do drukowania dokumentów.

## <a name="service-overview"></a>Ogólne informacje o usługach
Kiedy dokumenty generowane przez hostowane aplikacje oczekują na wydrukowanie na urządzeniu sieciowym, są przechowywane w magazynie obiektów blob usługi Azure. [Agent rozsyłania dokumentów](install-document-routing-agent.md) używa uwierzytelniania Azure do ustanawiania bezpiecznego kanału do usług platformy Azure. **Sekwencja wykonania**

1.  Raport jest generowany przez program Microsoft SQL Server Reporting Services (SSRS) i przechowywany w magazynie obiektów blob usługi Azure. Ustawienia dołączonej drukarki są przechowywane razem z dokumentem.
2.  Agent rozsyłania dokumentów wysyła zapytania do kolejki magistrali usług Azure o aktywne zadania.
3.  Dokument jest pobierany przez Agenta rozsyłania dokumentów i buforowany na drukarce sieciowej.

Rozwiązanie oparte na kliencie pozwala klientom zarządzać skalą potrzeb w zakresie drukowania. Użytkownicy, którzy drukują bardzo dużo, mogą zainstalować wiele Agentów rozsyłania dokumentów, aby zwiększyć liczbę równoczesnych operacji drukowania. Z drugiej strony niektórzy użytkownicy wymagają bardzo niewiele instalacji Agenta rozsyłania dokumentów do obsługi przewidywanych potrzeb w zakresie drukowania.

### <a name="service-components-for-network-printing"></a>Składniki usługowe do drukowania w sieci

Na poniższym diagramie przedstawiono podstawowe składniki pomagające obsługiwać operacje drukowania przez sieć. [![service-components-for-network-printing\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png) Należy zwrócić uwagę, że jedną drukarkę można zarejestrować w wielu Agentach rozsyłania dokumentów. Aby odczytywać preferencje drukarki, hostowana usługa używa ścieżki sieciowej, która unikatowo identyfikuje każdą drukarkę sieciową. W związku z tym nawet jeśli drukarka jest zarejestrowana na wielu klientach, pojawia się jako jedna opcja wyboru na liście dostępnych drukarek w aplikacjach rozwiązania Finance and Operations.




