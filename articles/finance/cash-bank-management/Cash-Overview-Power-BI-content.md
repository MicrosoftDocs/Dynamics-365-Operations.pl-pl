---
title: Pakiet zawartości Przegląd środków pieniężnych dla usługi Power BI
description: W tym temacie opisano pakiet zawartość Przegląd środków pieniężnych dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.
author: saraschi2
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6ad99f00438b0f9ccbf84e504219e39aa49f2bc1
ms.sourcegitcommit: 14b554b43b9d86152ef27fdde6141589bcaf1161
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/16/2020
ms.locfileid: "3598140"
---
# <a name="cash-overview-power-bi-content"></a>Pakiet zawartości Przegląd środków pieniężnych dla usługi Power BI

[!include [banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartości **Przegląd środków pieniężnych** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości **Przegląd środków pieniężnych** dla usługi Power BI jest przeznaczony dla osób odpowiedzialnych za zarządzanie gotówką w swoich organizacjach. Pakiet zawartości **Przegląd środków pieniężnych** dla usługi Power BI zapewnia wgląd w przepływy środków pieniężnych w firmie. Dostarcza również prognoz, które mogą pomóc podejmować lepsze decyzje i w efekcie optymalizować przepływ środków pieniężnych. Można analizować środki pieniężne według firm, walut i rachunków bankowych, aby lepiej zrozumieć przyczyny nadwyżek i niedoborów.

## <a name="setup-needed-to-view-power-bi-content"></a>Konfiguracja potrzebna do wyświetlenia zawartości Power BI.

Aby dane były wyświetlane w przeglądach Power BI **środków pieniężnych** i **zarządzania bankami**, należy zastosować następującą konfigurację.

1. Otwórz **Administracja Systemu > Konfiguracja > Parametry Systemu** i ustaw **Walutę systemu** oraz **Kurs wymiany systemu**.
2. Umożliwia przejście do **Księga główna > Kalendarze > Kalendarze obrachunkowe** w celu weryfikacji dat kalendarza obrachunkowego przypisanych do aktywnego okresu.
3. Otwórz **Księga ogólna > Konfiguracja > Księga** i ustaw **Waluta księgowa** oraz **Typ kursu wymiany**.
4. Zdefiniuj kursy wymiany między walutami transakcji a walutą księgową, walutą księgową a walutą systemu oraz walutą księgową oraz walutami banku. Żeby to zrobić, otwórz **Księga Ogólna > Waluty > Kursy wymiany walut**.
5. Skonfiguruj i uruchom proces Prognozy Przepływów Pieniężnych. Więcej informacji na temat uruchamiania Prognozy przepływów pieniężnych znajdziesz: [Prognozy przepływów pieniężnych](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting). 
6. Otwórz **Administracja Systemu > Konfiguracja > Sklep podmiotu** i odśwież łączny wskaźnik **CustCollectionsBIMeasurements**.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI

Raporty z zawartości **Przegląd środków pieniężnych** dla usługi Power BI są wyświetlane w obszarach roboczych **Przegląd środków pieniężnych** i **Zarządzanie rachunkami bankowymi**.

Aby wyświetlić raporty prognozowania przepływów pieniężnych z danymi, najpierw należy uruchomić proces obliczania prognozy za pomocą funkcji **Oblicz prognozy przepływów pieniężnych** z obszaru Zarządzanie gotówką i bankami. Należy to zrobić dla każdej firmy uwzględnionej w prognozie.  Następnie należy odświeżyć zagregowaną miarę LedgerCovLiquidityMeasurement na stronie **Magazyn jednostek**.  

Dla celów demonstracyjnych można za pomocą strony **Generuj dane** dodać dane demonstracyjne prognozowania przepływów pieniężnych z modułu Dane demonstracyjne.  Ten skrypt spowoduje wstawienie danych do tabel prognozowania przepływów pieniężnych, tak aby szybko wypełnić pola informacji niezbędnych dla raportów.  Ten moduł jest dostępny tylko wtedy, gdy w środowisku masz wdrożony model pakietu danych demonstracyjnych. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty dostępne w pakiecie zawartości dla usługi Power BI

W poniższej tabeli przedstawiono szczegóły dotyczące mierników, które znajdują się na każdej stronie raportu w pakiecie zawartości **Przegląd środków pieniężnych** dla usługi Power BI.

| Raport                                | Zawartość |
|---------------------------------------|----------|
| Przegląd środków pieniężnych — wszystkie firmy         | <ul><li>Przychody i rozchody w walucie systemowej</li><li>Prognozowane salda w walutach</li><li>Łączne saldo rachunków bankowych w walucie systemowej</li><li>Saldo wg firmy</li><li>Dzisiejsze saldo rzeczywiste w porównaniu z prognozowanym w walucie konta bankowego</li></ul> |
| Przegląd środków pieniężnych — bieżąca firma       | <ul><li>Przychody i rozchody w walucie rozliczeniowej</li><li>Prognozowane salda w walutach</li><li>Łączne saldo rachunków bankowych w walucie rozliczeniowej</li><li>Dzisiejsze saldo rzeczywiste w porównaniu z prognozowanym w walucie konta bankowego</li></ul> |
| Prognoza przepływów pieniężnych — wszystkie firmy    | <ul><li>Przychody i rozchody w walucie systemowej</li><li>Dzienne podsumowanie prognoz</li><li>Szczegóły prognozy</li></ul> |
| Prognoza przepływów pieniężnych — waluta firmy | <ul><li>Przychody i rozchody w walucie rozliczeniowej</li><li>Dzienne podsumowanie prognoz</li><li>Szczegóły prognozy</li></ul> |
| Prognoza dla waluty                     | <ul><li>Prognozowane salda w walutach</li><li>Dzienne podsumowanie waluty</li><li>Szczegóły prognozy</li></ul> |
| Salda rachunków bankowych                         | <ul><li>Łączne saldo rachunków bankowych w walucie systemowej</li><li>Saldo wg firmy</li><li>Dzisiejsze saldo rzeczywiste w porównaniu z prognozowanym w walucie konta bankowego</li><li>Saldo wg konta bankowego</li><li>Saldo wg waluty</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

W poniższej tabeli przedstawiono jednostki, na których bazuje pakiet zawartości **Przegląd środków pieniężnych** dostępny dla usługi Power BI.

| Jednostka                                                                          | Zawartość |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | Firmy, według których będą filtrowane raporty |
| LedgerCovLiquidityMeasurement\_Date                                             | Daty, według których będą filtrowane raporty |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Rzeczywiste saldo rachunków bankowych w porównaniu z ostatnim prognozowanym saldem rachunków bankowych |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Szczegóły prognozowanej transakcji |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Zsumowane przychody, rozchody i salda środków pieniężnych w walucie rozliczeniowej każdej firmy |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Zsumowane przychody, rozchody i salda środków pieniężnych w walucie systemowej dla wszystkich firm |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Zsumowana kwota netto transakcji oraz salda walut w walutach transakcji |
