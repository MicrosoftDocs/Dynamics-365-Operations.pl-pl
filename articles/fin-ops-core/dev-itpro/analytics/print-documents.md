---
title: Omówienie drukowania dokumentu
description: Dokumenty można drukować przy użyciu drukarki lokalnej lub urządzenia podłączonego do sieci. Ten artykuł zawiera omówienie sposobu drukowania dokumentów.
author: TJVass
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: IT Pro, Application User
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.custom: 69161
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c8475e26d9a2234d4c429ef1b5e482ac06fde08
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182906"
---
# <a name="document-printing-overview"></a>Omówienie drukowania dokumentu

[!include [banner](../includes/banner.md)]

Dokumenty można drukować przy użyciu drukarki lokalnej lub urządzenia podłączonego do sieci. Ten artykuł zawiera omówienie sposobu drukowania dokumentów.

## <a name="printing-overview"></a>Ogólne informacje o drukowaniu

Aplikacja zawiera zintegrowane usługi i aplikacje klienckie, które pozwalają łatwo generować, przechowywać i rozpowszechniać dokumenty wspierające działalność biznesową. Dokumenty można drukować przy użyciu drukarki lokalnej lub urządzenia podłączonego do sieci. Ponadto strony i raporty można eksportować bezpośrednio z klienta jako pliki PDF lub dokumenty Microsoft Office. Funkcja rozproszonego obciążenia pracą pozwala drukować dokumenty biznesowe bezpośrednio z urządzenia przenośnego przy użyciu zasobów sieciowych. Wymagania dotyczące drukowania mogą się różnić, jednak zwykle we wszystkich branżach trzeba tworzyć drukowane kopie dokumentów biznesowych przy użyciu aplikacji. Drukowanie dokumentów na urządzeniach sieciowych z hostowanych aplikacji stwarza unikatowe wyzwania. Oto kilka przykładów:

- Sterowniki druku mogą być niedostępne na urządzeniu użytkownika.
- Urządzenie użytkownika może nie być podłączone do firmowej sieci.

Używając dedykowanego hosta i wykonując kilka prostych kroków, administratorzy systemu mogą tak skonfigurować wdrożenia, aby użytkownicy mogli drukować bezpośrednio z aplikacji biznesowych na urządzeniach sieciowych.

### <a name="application-printing-scenarios"></a>Scenariusze drukowania zgłoszeń 

W poniższej tabeli opisano trzy główne scenariusze drukowania.

| Scenariusz                        | Cel                                                      | Rozwiązanie |
|---------------------------------|-----------------------------------------------------------|----------|
| 1. Drukowanie tego, co widać        | Drukowanie zawartości obecnie wyświetlanej w przeglądarce.             | Dla przeglądarki jest generowana wersja strony sieci Web specjalnie przystosowana do druku. |
| 2. Interaktywne drukowanie         | Drukowanie precyzyjnie zdefiniowanego dokumentu na lokalnie podłączonym urządzeniu. | Można wyeksportować wersję PDF raportu i pobrać ją do przeglądarki. |
| 3. Drukowanie na urządzeniu sieciowym | Wysyłanie precyzyjnie zdefiniowanego dokumentu do drukarki w domenie.     | Precyzyjnie zdefiniowany dokument jest wysyłany do aplikacji klienckiej, która jest uruchomiona na serwerze umieszczonym w domenie odbiorcy. |

Ponieważ stosowane rozwiązanie różni się w zależności od scenariusza, aplikacje zawierają wbudowane usługi i narzędzia pomagające użytkownikom osiągnąć wyznaczone cele:

- **Scenariusz 1** jest obsługiwany przez renderowanie w przeglądarce zawartości z klienta obsługującego format HTML5.
- **Scenariusz 2** korzysta z aplikacji klienckich i usługi Microsoft Office 365.
- **Scenariusz 3** wymaga obsługi ze strony aplikacji klienckich oraz usług hostowanych na platformie Microsoft Azure.

Oprócz platformy wdrożonej w ramach subskrypcji usługi Azure odbiorcy mogą korzystać z aplikacji rozwiązania Finance and Operations, które są zintegrowane z platformą Azure i pochodzą od jej producenta, co ułatwia korzystanie z urządzeń w domenie do drukowania dokumentów.

## <a name="service-overview"></a>Ogólne informacje o usługach
Kiedy dokumenty generowane przez hostowane aplikacje oczekują na wydrukowanie na urządzeniu sieciowym, są przechowywane w magazynie obiektów blob usługi Azure. [Agent rozsyłania dokumentów](install-document-routing-agent.md) używa uwierzytelniania Azure do ustanawiania bezpiecznego kanału do usług platformy Azure.

**Sekwencja wykonania**

1. Raport jest generowany przez program Microsoft SQL Server Reporting Services (SSRS) i przechowywany w magazynie obiektów blob usługi Azure. Ustawienia dołączonej drukarki są przechowywane razem z dokumentem.
2. Agent rozsyłania dokumentów wysyła zapytania do kolejki magistrali usług Azure o aktywne zadania.
3. Dokument jest pobierany przez Agenta rozsyłania dokumentów i buforowany na drukarce sieciowej.

Rozwiązanie oparte na kliencie pozwala klientom zarządzać skalą potrzeb w zakresie drukowania. Użytkownicy, którzy drukują bardzo dużo, mogą zainstalować wiele Agentów rozsyłania dokumentów, aby zwiększyć liczbę równoczesnych operacji drukowania. Z drugiej strony niektórzy użytkownicy wymagają bardzo niewiele instalacji Agenta rozsyłania dokumentów do obsługi przewidywanych potrzeb w zakresie drukowania.

### <a name="service-components-for-network-printing"></a>Składniki usługowe do drukowania w sieci

Na poniższym diagramie przedstawiono podstawowe składniki pomagające obsługiwać operacje drukowania przez sieć.

[![service-components-for-network-printing\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)

Należy zwrócić uwagę, że jedną drukarkę można zarejestrować w wielu Agentach rozsyłania dokumentów. Aby odczytywać preferencje drukarki, hostowana usługa używa ścieżki sieciowej, która unikatowo identyfikuje każdą drukarkę sieciową. W związku z tym nawet jeśli drukarka jest zarejestrowana na wielu klientach, pojawia się jako jedna opcja wyboru na liście dostępnych drukarek w aplikacjach.
