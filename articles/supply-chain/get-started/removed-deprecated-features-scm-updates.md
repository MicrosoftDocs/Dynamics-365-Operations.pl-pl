---
title: Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Supply Chain Management
description: W tym artykule opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia w Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 06/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 722b34e89a54715db39259549c11a78d69d2b4d3
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739878"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Ten artykuł zostanie zaktualizowany, jeśli w systemie Dynamics 365 Supply Chain Management zostaną udokumentowane nowe lub wycofane funkcje.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu.

> [!NOTE]
> Szczegółowe informacje o obiektów w aplikacji finansowych i operacyjnych można znaleźć w [raportach z wykazami parametrów technicznych](/dynamics/s-e/). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji finansowych i operacyjnych.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10029-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Supply Chain Management 10.0.29

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Zamówienia przeniesienia zapasów, które mają podatek od ceny przeniesienia

| &nbsp;  | &nbsp;  |
|---|---|
| **Przyczyna wycofania/usunięcia** | Zamówienia [przeniesienia zapasów, które mają podatek w funkcji ceny](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md) przeniesienia, są zastępowane [przez funkcję Zamówienia przeniesienia zapasów dla Indii](../../finance/localizations/apac-ind-stock-transfer.md). |
| **Zamieniona przez inną funkcję?**   | Tak, zamówienia [przeniesienia zapasów, które mają podatek w funkcji ceny](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md) przeniesienia, są zastępowane [przez funkcję Zamówienia przeniesienia zapasów dla Indii](../../finance/localizations/apac-ind-stock-transfer.md). |
| **Powiązane obszary produktów** | Supply Chain Management - zapasy |
| **Opcja wdrażania** | Wdrożenie w chmurze i lokalne |
| **Stan** | <p>Są wycofane. Zlecenia przelewu *Zlecenia przeniesienia zapasów, które mają podatek od ceny transferowej* nie otrzymają wsparcia z poprawkami błędów i poprawkami bezpieczeństwa.</p><p>Po kwietniu 2023 roku odbiorcy zostaną proszeni o korzystanie z poprawionej funkcjonalności *Zamówienia przeniesienia zapasów dla Indii* domyślnie. Po październiku 2023 r. nie będzie już dostępna funkcja *Zleceń przeniesienia zapasów, które mają podatek od ceny przelewu*, a klienci zostaną poproszeni o przejście do ulepszonej funkcji *Zamówienia przeniesienia zapasów dla Indii*.</p><p>Aby uzyskać więcej informacji, zobacz [Zamówienia przeniesienia zapasów dla Indii](../../finance/localizations/apac-ind-stock-transfer.md).</p> |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10019-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Supply Chain Management 10.0.19

### <a name="job-card-device"></a>Urządzenie karty zadań

| &nbsp;  | &nbsp;  |
|---|---|
| **Przyczyna wycofania/usunięcia** | [Urządzenie karty zadań](../production-control/config-job-card-device.md) jest zastępowane przez nowy [interfejs wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md). |
| **Zamieniona przez inną funkcję?**   | Tak, [urządzenie karty zadań](../production-control/config-job-card-device.md) zostanie zastąpione przez nowy [interfejs wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md). |
| **Powiązane obszary produktów** | Supply Chain Management — kontrola produkcji |
| **Opcja wdrażania** | Wdrożenie w chmurze i lokalne |
| **Stan** | Wycofane. Urządzenie karty zadań będzie objęte pomocą techniczną z poprawkami usterki i zabezpieczeń, ale udoskonalenia funkcji nie będą już dostarczane. Po kwietniu 2022 r. urządzenie karty zadań nie będzie już obsługiwane, a klienci zostaną poproszeni o przejście na nowy interfejs wykonywania hal produkcyjnych. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Supply Chain Management 10.0.18

### <a name="supply-chain-management--warehousing-the-warehouse-app"></a><a name="wma"></a>Supply Chain Management- magazynowanie (aplikacja magazynowa)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Z dniem 2021 kwietnia rozwiązanie *Supply Chain Management — Magazynowanie* (aplikacja magazynu) jest przestarzałe i nie będzie obsługiwane po kwietniu 2022 roku. Zostanie ona zastąpiona przez *aplikację mobilną Warehouse Management*, która została wydana w wersji 10.0.17 Supply Chain Management. Nowa aplikacja jest pełną wymianą, ale korzysta z tej samej struktury źródłowej, co ułatwia migrację. W razie potrzeby obie aplikacje mogą być używane side-by-side, aby pomagać użytkownikom stopniowo dostosowywać się do potrzeb nowej aplikacji.<br><br>Jeśli chcesz uzyskać informacje dotyczące konfigurowania aplikacji Warehouse Management, zobacz temat [aplikacji mobilnej Warehouse Management](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application) i [Instalowanie i łączenie aplikacji mobilnej Zarządzanie magazynem](../warehousing/install-configure-warehouse-management-app.md). |
| **Zamieniona przez inną funkcję?**   | Tak, zastąpiono nową aplikacją mobilną Warehouse Management. |
| **Powiązane obszary produktów**         | Supply Chain Management — aplikacja magazynowa |
| **Opcja wdrażania**              | Wdrożenie w chmurze i lokalne |
| **Stan**                         | Wycofane. Aplikacja magazynu będzie otrzymywać pomoc techniczną z poprawkami usterki i zabezpieczeń, ale udoskonalenia funkcji nie zostaną już dostarczone. Po kwietniu 2022 r. Stara aplikacja magazynowa nie będzie już obsługiwana, a klienci zostaną poproszeni o przejście do nowej aplikacji mobilnej Warehouse Management. Stara aplikacja magazynu zostanie usunięta ze sklepu Microsoft Store i Google Play.  |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Supply Chain Management 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Wsparcie Internet Explorer 11 dla Dynamics 365 jest przestarzałe

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Począwszy od grudnia 2020 r., obsługa Microsoft Internet Explorer 11 dla wszystkich produktów Dynamics 365 jest przestarzała, a Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021 r.<br><br>Będzie to miało wpływ na klientów, którzy używają produktów Dynamics 365 zaprojektowanych do używania za pośrednictwem interfejsu Internet Explorer 11. Po sierpniu 2021, Internet Explorer 11 nie będzie obsługiwany przez produkty Dynamics 365. |
| **Zamieniona przez inną funkcję?**   | Zaleca się, aby klienci przeszli na Microsoft Edge.|
| **Powiązane obszary produktów**         | Wszystkie produkty Dynamics 365 |
| **Opcja wdrażania**              | Wszyscy|
| **Stan**                         | Wycofane. Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Użycie wbudowanego aparatu planowania głównego Supply Chain Management na potrzeby scenariuszy dotyczących produkcji

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Aby zwiększyć wydajność i zminimalizować obciążenie pracą bazy danych SQL podczas przebiegów planowania głównego, aparat planowania głównego aplikacji Supply Chain Management jest zastępowany przez optymalizację planowania. Optymalizacja planowania umożliwia szybkie przebiegi planowania, które można wykonywać nawet w godzinach pracy. Pozwala to planistom na natychmiastowe reagowanie na zmiany wprowadzone w parametrach popytu lub planowania. |
| **Zamieniona przez inną funkcję?**   | Tak, optymalizacja planowania zastąpi istniejący wbudowany aparat planowania głównego aplikacji Supply Chain Management. |
| **Powiązane obszary produktów**         | Supply Chain Management — planowanie główne |
| **Opcja wdrażania**              | Tylko chmura. Optymalizacja planowania nie jest obsługiwana w przypadku wdrożeń lokalnych. |
| **Stan**                         | Wycofane. Do 1 kwietniu 2022 r. scenariusze produkcji nie będą już obsługiwane za pomocą wbudowanego aparatu planowania głównego aplikacji Supply Chain Management. Od tego dnia firma Microsoft zaprzestanie wszelkich aktywnych prac nad scenariuszami produkcyjnymi dla wbudowanego silnika planowania, nie wyda żadnych nowych funkcji i wyda jedynie krytyczne poprawki błędów. Po tej dacie wszystkie firmy, które wymagają obsługi scenariuszy produkcyjnych, muszą używać Optymalizacji planowania do swoich obliczeń planowania głównego. Optymalizacja planowania ma w pełni obsługiwać scenariusze produkcji do października 2022 roku. Aby uzyskać więcej informacji, zobacz temat [Omówienie wycofanego planowania głównego](../master-planning/deprecated-master-planning-overview.md).<br><br>Firmy z lokalnymi wdrożeniami rozwiązania Supply Chain Management mogą nadal używać wbudowanego głównego aparatu planowania w scenariuszach produkcyjnych po kwietniu 2022 roku. Nie będą jednak wprowadzane dodatkowe ulepszenia funkcji. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Supply Chain Management 10.0.11

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Użycie wbudowanego aparatu planowania głównego Supply Chain Management na potrzeby scenariuszy dotyczących dystrybucji

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Aby zwiększyć wydajność i zminimalizować obciążenie pracą bazy danych SQL podczas przebiegów planowania głównego, aparat planowania głównego aplikacji Supply Chain Management jest zastępowany przez optymalizację planowania. Optymalizacja planowania umożliwia szybkie przebiegi planowania, które można wykonywać nawet w godzinach pracy. Pozwala to planistom na natychmiastowe reagowanie na zmiany wprowadzone w parametrach popytu lub planowania. |
| **Zamieniona przez inną funkcję?**   | Tak, optymalizacja planowania zastąpi istniejący wbudowany aparat planowania głównego aplikacji Supply Chain Management. |
| **Powiązane obszary produktów**         | Supply Chain Management — planowanie główne |
| **Opcja wdrażania**              | Tylko chmura. Optymalizacja planowania nie jest obsługiwana w przypadku wdrożeń lokalnych. |
| **Stan**                         | Wycofane. Do 1 kwietniu 2021 r. scenariusze dystrybucji nie będą już obsługiwane za pomocą wbudowanego aparatu planowania głównego aplikacji Dynamics 365 Supply Chain Management. W scenariuszach dystrybucji klienci muszą korzystać z optymalizacji planowania podczas obliczeń planowania głównego. Aby uzyskać więcej informacji, zobacz temat [Omówienie wycofanego planowania głównego](../master-planning/deprecated-master-planning-overview.md). Klienci z wdrożeniami lokalnymi aplikacji Dynamics 365 Supply Chain Management będą mogli nadal korzystać z aparatu planowania głównego aplikacji Supply Chain Management w scenariuszach dystrybucji po kwietniu 2021 r. Nie będą jednak wprowadzane dodatkowe ulepszenia funkcji. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach

Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

