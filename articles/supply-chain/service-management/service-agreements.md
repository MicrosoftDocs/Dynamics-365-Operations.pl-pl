---
title: Omówienie opracowania i ustanawiania przeglądów umów serwisowych
description: Umowy serwisowe pozwalają definiować zasoby, które mają być używane podczas typowej wizyty serwisowej, i sposób fakturowania tych zasobów dla klienta.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd17cc0304d58d27afe2cededa5bc0b96557b5e9
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981999"
---
# <a name="develop-and-establish-service-agreements-overview"></a>Omówienie opracowania i ustanawiania przeglądów umów serwisowych

[!include [banner](../includes/banner.md)]

Umowy serwisowe pozwalają definiować zasoby, które mają być używane podczas typowej wizyty serwisowej, i sposób fakturowania tych zasobów dla klienta.

Każda umowa serwisowa jest dołączona do projektu, za pośrednictwem którego transakcje są księgowane i fakturowane. Jednak transakcje ze zlecenia serwisowego można również fakturować bezpośrednio w projekcie bez konieczności łączenia zlecenia serwisowego z umową serwisową. Z tej opcji można skorzystać, jeśli zlecenie serwisowe dotyczy tylko jednorazowej wizyty serwisowej i jeśli konieczność szybkiego przetworzenia transakcji serwisowych jest ważniejsza niż konieczność rejestrowania szczegółowych informacji umowy serwisowej dotyczących klienta w określonym czasie.

## <a name="service-agreement"></a>Umowa serwisowa

W każdej umowie serwisowej trzeba określić projekt, identyfikator umowy serwisowej i grupę umów serwisowych. Dzięki grupie umów serwisowych można sortować i porządkować umowy serwisowe.

Nagłówek umowy serwisowej zawiera ustawienia dotyczące wszystkich dołączonych wierszy umowy:

-  Czy umowa serwisowa jest zawieszona. Jeśli tak, nie można na jej podstawie generować zleceń serwisowych.
-  Czas trwania umowy serwisowej.
-  Sposób łączenia wierszy zleceń serwisowych w zlecenia serwisowe.
-  Czy umowa serwisowa jest szablonem.

W nagłówku umowy serwisowej można również skonfigurować wszystkie przedmioty serwisu i zadania serwisowe, które mają zastosowanie do umowy serwisowej. W tym celu należy wprowadzić konkretne zadania serwisowe lub przedmioty serwisu, które mają zostać dołączone do różnych wierszy umowy.

W nagłówku umowy serwisowej można także kopiować wiersze umowy serwisowej i wiersze szablonu usługi do bieżącej umowy serwisowej.

W programie można zawieszać umowę serwisową oraz blokować jej poszczególne wiersze.

Zaznaczenie pola wyboru **Zawieszone** w umowie serwisowej uniemożliwi wykonywanie następujących operacji:

-    Automatyczne lub ręczne tworzenie zleceń serwisowych z poziomu umowy serwisowej.

Zaznaczenie pola wyboru **Zablokowane** w wierszu umowy serwisowej uniemożliwi wykonywanie następujących operacji:

-    Automatyczne lub ręczne tworzenie zleceń serwisowych z poziomu wiersza umowy serwisowej.
-    Kopiowanie wiersza umowy serwisowej do innej umowy serwisowej lub zlecenia serwisowego.


> [!NOTE]
> Jeśli umowa serwisowa zostanie zawieszona, wszystkie dołączone wiersze są blokowane niezależnie od ich indywidualnego statusu.

## <a name="service-agreement-lines"></a>Wiersze umowy serwisowej

Każdy wiersz umowy serwisowej zawiera szczegółowy opis proponowanych czynności serwisowych. Wiersze te zawierają następujące ustawienia:

-  typ transakcji i opis typu transakcji;
-  pracownik wykonujący czynności serwisowe;
-  przedmioty, których dotyczą czynności serwisowe wykonywane na mocy umowy serwisowej;
-  częstotliwość, z jaką są wykonywane czynności oraz z jaką są rejestrowane towary, wydatki i opłaty;
-  okno czasowe, w którym można grupować wiersze zlecenia serwisowego w jedno zlecenie serwisowe;
-  zadania serwisowe, przy użyciu których grupuje się zbiory wierszy umowy w zadania robocze oraz przedstawia technikom serwisu i klientom podsumowanie informacji o zadaniu serwisowym, które ma zostać wykonane;
-  informacja, czy wiersz jest zablokowany — jeśli tak, nie można tworzyć zleceń serwisowych dla danego wiersza;
-  ustawienia projektu, takie jak kategoria i właściwość wiersza.

## <a name="related-topics"></a>Powiązane tematy

[Tworzenie umów o świadczenie usług](create-service-agreements.md)
