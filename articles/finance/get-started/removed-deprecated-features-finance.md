---
title: Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Finance
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 12/07/2020
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
ms.openlocfilehash: a406db6d78302fa05596a58fffb7464222d4bfea
ms.sourcegitcommit: 069ed5789517b550065e5e2317658fec4027359e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2020
ms.locfileid: "4689501"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Finance.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

> [!NOTE]
> Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.16

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>Format raportowania elektronicznego „Format eksportu transakcji księgi (BE)” i odpowiadający mu model „Eksport transakcji księgi (BE)” dla Belgii

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym formatem ER w modelu „Standardowy plik audytu (SAF-T)”.  |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Przestarzałe: Do 1 grudnia 2021 chcemy wycofać format raportowania elektronicznego (ER) „Format eksportu transakcji księgi (BE)” i odpowiadający mu model „Eksport transakcji księgi (BE)”. Zamiast modelu „Standardowy plik audytu (SAF-T)” zostanie wprowadzony nowy format „Eksport danych księgi głównej (BE)” razem z mapowaniem „Mapowanie modelu danych księgi głównej”. |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>Raport „VAT 100” dla Wielkiej Brytanii w formacie SSRS

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym formatem ER — „Deklaracja VAT w formacie Excel (UK)” w modelu „Model deklaracji podatkowej”.  |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Przestarzałe: Do 1 grudnia 2021 r. chcemy wycofać sprawozdanie „Raport VAT 100” w formacie SSRS. Nowy format „Deklaracja VAT w formacie Excel (UK)” w modelu „Model deklaracji podatkowej” został wprowadzony w [funkcji VAT w MTD](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Wsparcie Internet Explorer 11 dla Dynamics 365 jest przestarzałe

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Począwszy od grudnia 2020 r., obsługa Microsoft Internet Explorer 11 dla wszystkich produktów Dynamics 365 jest przestarzała, a Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021 r.<br><br>Będzie to miało wpływ na klientów, którzy używają produktów Dynamics 365 zaprojektowanych do używania za pośrednictwem interfejsu Internet Explorer 11. Po sierpniu 2021, Internet Explorer 11 nie będzie obsługiwany przez produkty Dynamics 365. |
| **Zamieniona przez inną funkcję?**   | Zaleca się, aby klienci przeszli na Microsoft Edge.|
| **Powiązane obszary produktów**         | Wszystkie produkty Dynamics 365 |
| **Opcja wdrażania**              | Wszyscy|
| **Stan**                         | Wycofane. Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021.|

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]