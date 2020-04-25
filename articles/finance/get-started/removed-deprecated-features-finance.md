---
title: Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Finance
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: aebce032d7d780b296ba74fea4467425a3cbe1a7
ms.sourcegitcommit: 4e9b3746790355f9f72bbfddc099c4065a49ad63
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/30/2020
ms.locfileid: "3175115"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Finance.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

> [!NOTE]
> Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.12

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Polskie raporty SSRS: Rejestr VAT sprzedaży, Rejestr VAT zakupów, rejestru VAT podsumowania UE — odwołanie do funkcji PL-00014

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa nie jest wymagana prawnie.  |
| **Zamieniona przez inną funkcję?**   | Tak (format programu Excel dla standardowego pliku audytu: Deklaracja VAT — JPK_VDEK) |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: do 1 lipca 2021, nie planujemy obsługiwać raportów SSRS: **Rejestr VAT sprzedaży, Rejestr VAT zakupów, zbiorczy Rejestr VAT dla UE — odwołanie do funkcji PL-00014**. Przykład formatu programu Excel dla standardowego pliku audytu z uwzględnieniem deklaracji VAT (JPK_VDEK) zostanie wprowadzony w zamian. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.11

### <a name="norwegian-standard-main-accounts"></a>Konto główne norweskiego standardu

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Przeprojektowanie  |
| **Zamieniona przez inną funkcję?**   | Tak (zamieniono na parametry określone dla aplikacji formatu ER) |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: w kwietniu 1, 2021, nie planujemy już obsługi funkcji związanych ze standardowymi kontami głównymi: pole odwołania, tabela pokrewna, jednostka danych. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.7

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Okno dialogowe zmiana żądania przepływu pracy nie zawiera już listy rozwijanej wyboru użytkownika
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zmieniono na funkcję z opcją wyboru grup kont.  |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Przepływ pracy |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: Do 1 grudnia 2020 r. planujemy zakończyć obsługę chińskich typy załączników bez opcji wyboru grup kont. Więcej szczegółów dotyczących nowego projektu funkcji można znaleźć w temacie dotyczącym [nowości w wersji 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach
Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).
