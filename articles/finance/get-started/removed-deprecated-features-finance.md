---
title: Usunięte lub przestarzałe funkcje w rozwiązaniu Dynamics 365 Finance
description: W tym artykule opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z aplikacji Dynamics 365 Finance.
author: kfend
ms.date: 10/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 25d13aa26565e5753b87c843b43cf46f8276b642
ms.sourcegitcommit: 6c05bcd27e6ee72f01cb66e2cfd1e929e0365830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/16/2022
ms.locfileid: "9854087"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Usunięte lub przestarzałe funkcje w rozwiązaniu Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

W tym artykule opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z aplikacji Dynamics 365 Finance.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

> [!NOTE]
> Szczegółowe informacje o obiektów w aplikacji finansowych i operacyjnych można znaleźć w [raportach z wykazami parametrów technicznych](/dynamics/s-e/global/axtechrefrep_61). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji finansowych i operacyjnych.

## <a name="features-removed-or-deprecated-in-the-finance-10031-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.31

### <a name="edifact-paymul-at-configuration-under-payment-model"></a>Konfiguracja EDIFACT PAYMUL (AT) w modelu płatności

| &nbsp;  | &nbsp;  |
|---|---|
| **Przyczyna wycofania/usunięcia** | Zostanie zastąpiony nowym formatem opartym na normie ISO 20022 pain.001.001.09. | 
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofane: W listopadzie 2022 roku banki w Austrii wycofają EDICFACT-PAYMUL dla płatności transgranicznych i zastąpią je wersją XML pain.001.001.09N. W repozytorium konfiguracji globalnej dodano nową konfigurację, która umożliwia użytkownikom zakończenie żądania płatności transgranicznych. |

## <a name="features-removed-or-deprecated-in-the-finance-10030-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.30

### <a name="revenue-recognition"></a>Rozpoznawanie przychodu

[Rozpoznawanie przychodu](../../finance/accounts-receivable/revenue-recognition-overview.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Przyczyna wycofania/usunięcia** |Zastąpiono poprawioną funkcjonalnością, [Rozliczanie subskrypcji](../../finance/accounts-receivable/subscription-billing-summary.md)
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów** | Zgłoszenie |
| **Opcja wdrażania** | Wszystko |
| **Stan** | Wycofane: od kwietnia 2023 roku funkcja Rozpoznawania przychodów w programie Dynamics 365 Finance nie będzie już otrzymywać pomocy technicznej dotyczącej poprawek błędów. Odbiorcy zostaną proszeni o korzystanie z poprawionej funkcjonalności [Rozliczanie subskrypcji](../../finance/accounts-receivable/subscription-billing-summary.md). W październiku 2023 roku funkcja Rozpoznawania przychodów nie będzie już dostępna. Odbiorcy zostaną proszeni o przeniesienie się do poprawionej funkcjonalności Rozliczanie subskrypcji. W przypadku funkcji pakietu jako części rozpoznania przychodów nie zaplanowano w tej chwili funkcji zastępczych.|

## <a name="features-removed-or-deprecated-in-the-finance-10029-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.29

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Zamówienia przeniesienia zapasów, które mają podatek od ceny przeniesienia

[Zamówienia przeniesienia zapasów, które mają podatek od ceny przeniesienia](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Przyczyna wycofania/usunięcia** | Zastąpiono poprawioną funkcjonalnością, [zamówienia przeniesienia zapasów dla Indii](../../finance/localizations/apac-ind-stock-transfer.md)|
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów** | Zgłoszenie |
| **Opcja wdrażania** | Wszystko |
| **Stan** | Wycofane: po kwietniu 2023 roku funkcje **Zlecenia przeniesienia zapasów, które mają podatek od ceny transferowej** nie otrzymają wsparcia z poprawkami błędów i poprawkami bezpieczeństwa. Odbiorcy zostaną proszeni o korzystanie z poprawionej funkcjonalności [Zamówienia przeniesienia zapasów dla Indii](../../finance/localizations/apac-ind-stock-transfer.md). Po październiku 2023 r. nie będzie już dostępna funkcja **Zleceń przeniesienia zapasów, które mają podatek od ceny przelewu**, a klienci zostaną poproszeni o przejście do ulepszonej funkcji. |

### <a name="bank-statement-import-and-export-of-positive-pay-file"></a>Import wyciągu bankowego i eksport pliku płatności dodatnich

| &nbsp;  | &nbsp;  |
|---|---|
| **Przyczyna wycofania/usunięcia** |Zastąpiono poprawioną funkcjonalnością, zaimportowano wyciągi bankowe i wyeksportowano pliki płatności dodatnich.| 
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofana: funkcjonalność XSLT importowania i eksportowania plików nie będzie już obsługiwać poprawek błędów i poprawek zabezpieczeń. Odbiorcy zostaną proszeni o korzystanie z poprawionych funkcji: [Konfigurowanie plików płatności dodatnich za pomocą raportowania elektronicznego](../../finance/accounts-payable/set-up-positive-pay-er.md) i [Konfigurowanie zaawansowanego importowania uzgodnienia konta bankowego za pomocą raportowania elektronicznego](../../finance/accounts-payable/import-bai2-er.md). Od września 2022 roku funkcja XSLT nie będzie już dostępna, a klienci zostaną poproszeni o przejście do poprawionej funkcjonalności.|


## <a name="features-removed-or-deprecated-in-the-finance-10026-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.26

### <a name="sales-tax-report-for-finland-design-based-on-reporting-codes"></a>Raport podatku dla Finlandii (projekt oparty na kodach raportowania)

[Raport podatku dla Finlandii](../localizations/emea-fin-sales-tax-payment-report-finland.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym projektem deklaracji VAT, [deklaracją VAT dla Finlandii](../localizations/emea-fin-vat-declaration.md). |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Przestarzałe: do 1 marca 2023 r. planujemy zaprzestać obsługi raportu podatku od sprzedaży dla Finlandii (układ raportu w języku fińskim). Wprowadzono nowe formaty ER **TXT — deklaracja VAT (FI)**, **Excel — deklaracja VAT (FI)** w modelu **Deklaracja podatkowa**. |

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.24

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>Raport podatku dla Szwecji (projekt oparty na kodach raportowania)

[Raport podatku dla Szwecji](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym projektem deklaracji VAT, [deklaracją VAT dla Szwecji](../localizations/emea-swe-vat-declaration-sweden.md) |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofano: do 1 grudnia 2022 r. zamierzamy nie obsługiwać już raportu podatku dla Szwecji (szwedzki układ raportu). Wprowadzono nowe formaty ER **XML — deklaracja VAT (SE)**, **Excel — deklaracja VAT (SE)** w modelu **Deklaracja podatkowa**. |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>Deklaracja VAT dla Austrii (projekt oparty na kodach raportowania)

[Szczegóły zestawienia VAT dla Austrii](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym projektem deklaracji VAT, [deklaracją VAT dla Austrii](../localizations/emea-aut-vat-declaration-austria.md) |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofano: do 1 grudnia 2022 roku zamierzamy nie obsługiwać już formatu ER **Deklaracja VAT (AT)** w **modelu deklaracji VAT**. Wprowadzono nowe formaty **XML — deklaracja VAT (AT)** i **Excel — deklaracja VAT (AT)** w modelu **Deklaracja podatkowa**. |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes-electronic-tax-declaration-log-menu-item-and-page-electronic-tax-declaration-setup-menu-item-and-page-german-report-layout-taxreport_de-ssrs-format"></a>Deklaracja ELSTER dla Niemiec (wzór oparty na kodach zgłoszeniowych), pozycja i strona menu \"Elektroniczna deklaracja podatkowa\", pozycja i strona menu \"Elektroniczna deklaracja podatkowa\", układ raportu dla Niemiec (TaxReport_DE) format SSRS

[Sprawozdanie podatku VAT](../localizations/emea-de-vat-declaration.md)</br>
[Konfigurowanie elektronicznej deklaracji podatkowej dla Niemiec](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym projektem deklaracji VAT, [deklaracją VAT dla Niemiec](../localizations/emea-deu-vat-declaration-germany.md) |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: Do 1 grudnia 2022 roku nie będziemy już wspierać formatu **Elster (DE)** Electronic Reporting (ER) oraz **modelu Elster**. Wprowadzono nowe formaty ER **XML — deklaracja VAT (DE)** i **Excel — deklaracja VAT (DE)** w modelu **Deklaracja podatkowa**. Nie będziemy również dłużej wspierać pozycji i strony menu **Podatek** \> **Deklaracje** \> **Podatek od sprzedaży** \> **Dziennik deklaracji podatku elektronicznego**, pozycji i strony menu **Podatek** \> **Ustawa** \> **Podatek od sprzedaży** \> **Ustawa deklaracji podatku elektronicznego**, **Podatek** \> **Ustawa** \> **Podatek od sprzedaży** \> **Elektroniczne zaświadczenia podatkowe** pozycja menu i strona, oraz niemiecki układ raportu (TaxReport\_DE) w formacie SQL Server Reporting Services (SSRS). Proces zgłaszania podatku VAT w Niemczech jest obsługiwany przez funkcjonalność [Przesyłanie wiadomości elektronicznych](../general-ledger/electronic-messaging.md). Więcej informacji znajdziesz na stronie [Deklaracja VAT dla Niemiec](../localizations/emea-deu-vat-declaration-germany.md). |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes-electronic-ob-declaration-menu-item-and-page-dutch-report-layout-taxreport_nl-ssrs-format"></a>Deklaracja OB dla Holandii (projekt oparty na kodach sprawozdawczych), pozycja i strona menu \"Elektroniczna deklaracja OB\", układ raportu holenderskiego (TaxReport_NL) w formacie SSRS

[Deklaracja OB](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono nowym projektem deklaracji VAT, [deklaracją VAT dla Holandii](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenie |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofano: do 1 grudnia 2022 roku zamierzamy nie obsługiwać już formatów ER **Deklaracja OB (NL)** i **Model deklaracji OB**. Wprowadzono nowe formaty ER **XML — deklaracja VAT (NL)** i **Excel — deklaracja VAT (NL)** w modelu **Deklaracja podatkowa**. Nie będziemy również dłużej wspierać pozycji i strony menu **Podatek** \> **Deklaracje** \> **Podatek od sprzedaży** \> **Elektroniczna deklaracja OB** oraz holenderskiego układu raportu (TaxReport_NL) w formacie SSRS. Proces zgłaszania podatku VAT w Holandii jest obsługiwany przez funkcjonalność [Przesyłanie wiadomości elektronicznych](../general-ledger/electronic-messaging.md). Więcej informacji znajdziesz na stronie [Deklaracja VAT dla Holandii](../localizations/emea-nl-vat-declaration-netherlands.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Finance 10.0.20

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>Konfiguracja formatu raportowania elektronicznego (ER) „Zapytanie o dane faktury RTIR (HU)”

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Wyłączone z elektronicznego przesyłania wiadomości przetwarzanie współdziałania z węgierskim systemem fakturowania online |
| **Zamieniona przez inną funkcję?**   | Nie |
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
| **Powiązane obszary produktów**         | Produkty Dynamics 365 Finance, Supply Chain Management i Project Operations|
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

