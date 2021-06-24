---
title: Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Finance
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Finance.
author: roschlom
ms.date: 04/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: e6a391b10ddaef79e68f47afae7d77135a1c333a
ms.sourcegitcommit: cb282e8d2306ab71adf80a84346a6863d2d019e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184132"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Finance.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

> [!NOTE]
> Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](/dynamics/s-e/global/axtechrefrep_61). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.20

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>Konfiguracja formatu raportowania elektronicznego (ER) „Zapytanie o dane faktury RTIR (HU)”

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Wyłączone z elektronicznego przesyłania wiadomości przetwarzanie współdziałania z węgierskim systemem fakturowania online |
| **Zamieniona przez inną funkcję?**   | Nr |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Wycofane: do 15 kwietnia 2022 r. Nie planujemy już obsługiwać konfiguracji formatu „Zapytania o dane faktury RTIR (HU)”. |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>„Francuski plik audytu FEC” — format raportowania elektronicznego (ER) dla Francji w formacie „niemiecki plik wyjściowy pliku inspekcji”

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym formatem „Plik inspekcji FEC (FR)” |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Wycofane: do 1 maja 2022 r. Planujemy zaprzestać obsługi formatu „francuskiego pliku kontrolnego FEC” dla Francji w formacie „niemieckiego pliku kontrolnego”. Zamiast tego wprowadzono nowy format pliku audytu FEC (FR) w „Modelu eksportu danych”. |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.17

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>Repozytorium usługi LCS jako opcja przechowywania w konfiguracjach raportowania elektronicznego

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Repozytorium globalne usługi Regulatory Configuration Service (RCS) zastąpiono |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Dynamics 365 Finance, Supply Chain Management i produkty w Project Operations|
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Wycofane: Do 1 kwietnia 2022 roku zamierzamy przestać obsługiwać repozytorium usługi Microsoft Dynamics Lifecycle Services (LCS) jako opcję przechowywania w konfiguracjach raportowania elektronicznego (ER). Nowe konfiguracje ER firmy Microsoft zostaną opublikowane w celu pobrania wyłącznie z repozytorium globalnym. Do repozytorium globalnego można uzyskać dostęp z produktów Dynamics 365 i usług RCS. Aby uzyskać więcej informacji, zobacz temat [Importowanie konfiguracji ER z usługi RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) i [Regulatory Configuration Service — deprecjacja pamięci Lifecycle Services](../localizations/rcs-lcs-repo-dep-faq.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.16

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>„Deklaracja VAT (CZ)” i „Eksport deklaracji kontrolnej (CZ)” Elektroniczne formaty raportowania dla Republiki Czeskiej

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowymi formatami |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Wycofane: do 22 stycznia 2022 r. Nie planujemy już obsługiwać formatów „deklaracja VAT (CZ)” i „eksport wyciągu kontrolnego (CZ)”. Raportowanie elektroniczne (ER). W modelu „deklaracja podatkowa” wprowadzono nowe formaty XML deklaracji VAT (CZ), deklaracji VAT Excel (CZ), deklaracji kontroli VAT XML (CZ). |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>Format raportowania elektronicznego „Format eksportu transakcji księgi (BE)” i odpowiadający mu model „Eksport transakcji księgi (BE)” dla Belgii

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym formatem ER w modelu „Standardowy plik audytu (SAF-T)”.  |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Przestarzałe: Do 1 grudnia 2021 chcemy wycofać format raportowania elektronicznego (ER) „Format eksportu transakcji księgi (BE)” i odpowiadający mu model „Eksport transakcji księgi (BE)”. Zamiast modelu „Standardowy plik audytu (SAF-T)” zostanie wprowadzony nowy format „Eksport danych księgi głównej (BE)” razem z mapowaniem „Mapowanie modelu danych księgi głównej”. |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>Raport „VAT 100” dla Wielkiej Brytanii w formacie SSRS

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym formatem ER — „Deklaracja VAT w formacie Excel (UK)” w modelu „Model deklaracji podatkowej”.  |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Przestarzałe: Do 1 grudnia 2021 r. chcemy wycofać sprawozdanie „Raport VAT 100” w formacie SSRS. Nowy format „Deklaracja VAT w formacie Excel (UK)” w modelu „Model deklaracji podatkowej” został wprowadzony w [funkcji VAT w MTD](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Wsparcie Internet Explorer 11 dla Dynamics 365 jest przestarzałe

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Począwszy od grudnia 2020 r., obsługa Microsoft Internet Explorer 11 dla wszystkich produktów Dynamics 365 jest przestarzała, a Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021 r.<br><br>Będzie to miało wpływ na klientów, którzy używają produktów Dynamics 365 zaprojektowanych do używania za pośrednictwem interfejsu Internet Explorer 11. Po sierpniu 2021, Internet Explorer 11 nie będzie obsługiwany przez produkty Dynamics 365. |
| **Zamieniona przez inną funkcję?**   | Zaleca się, aby klienci przeszli na Microsoft Edge.|
| **Powiązane obszary produktów**         | Wszystkie produkty Dynamics 365 |
| **Opcja wdrażania**              | Wszyscy|
| **Stan**                         | Wycofane. Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.12

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Nie są przestarzałe: Polskie raporty SSRS: Rejestr VAT sprzedaży, Rejestr VAT zakupów, rejestru VAT podsumowania UE — odwołanie do funkcji PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa nie jest wymagana prawnie.  |
| **Zamieniona przez inną funkcję?**   | Tak (format programu Excel dla standardowego pliku audytu: Deklaracja VAT — JPK_VDEK) |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Nie są przestarzałe: według stanu na 27 kwietnia 2021, planujemy kontynuowanie obsługi raportów SSRS: **Rejestr VAT sprzedaży, Rejestr VAT zakupów, zbiorczy Rejestr VAT dla UE — odwołanie do funkcji PL-00014**. Przykład formatu programu Excel dla standardowego pliku audytu z uwzględnieniem deklaracji VAT (JPK_VDEK) także został wprowadzony. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.11

### <a name="norwegian-standard-main-accounts"></a>Konto główne norweskiego standardu

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Przeprojektowanie  |
| **Zamieniona przez inną funkcję?**   | Tak (zamieniono na parametry określone dla aplikacji formatu ER) |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: w kwietniu 1, 2021, nie planujemy już obsługi funkcji związanych ze standardowymi kontami głównymi: pole odwołania, tabela pokrewna, jednostka danych. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.7

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Okno dialogowe zmiana żądania przepływu pracy nie zawiera już listy rozwijanej wyboru użytkownika

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zmieniono na funkcję z opcją wyboru grup kont.  |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Przepływ pracy |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: Do 1 grudnia 2020 r. planujemy zakończyć obsługę chińskich typy załączników bez opcji wyboru grup kont. Więcej szczegółów dotyczących nowego projektu funkcji można znaleźć w temacie dotyczącym [nowości w wersji 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach
Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
