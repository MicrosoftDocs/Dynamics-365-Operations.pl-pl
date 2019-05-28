---
title: Pakiet zawartości Przegląd środków pieniężnych dla usługi Power BI
description: W tym temacie opisano pakiet zawartość Przegląd środków pieniężnych dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.
author: saraschi2
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 5dccb5c5c6c336607603dfc7a935c039e5ac4aa5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568924"
---
# <a name="cash-overview-power-bi-content"></a>Pakiet zawartości Przegląd środków pieniężnych dla usługi Power BI

[!include [banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartości **Przegląd środków pieniężnych** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości **Przegląd środków pieniężnych** dla usługi Power BI jest przeznaczony dla osób odpowiedzialnych za zarządzanie gotówką w swoich organizacjach. Pakiet zawartości **Przegląd środków pieniężnych** dla usługi Power BI zapewnia wgląd w przepływy środków pieniężnych w firmie. Dostarcza również prognoz, które mogą pomóc podejmować lepsze decyzje i w efekcie optymalizować przepływ środków pieniężnych. Można analizować środki pieniężne według firm, walut i rachunków bankowych, aby lepiej zrozumieć przyczyny nadwyżek i niedoborów.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI

Raporty z zawartości **Przegląd środków pieniężnych** dla usługi Power BI są wyświetlane w obszarach roboczych **Przegląd środków pieniężnych** i **Zarządzanie rachunkami bankowymi**.

Aby wyświetlić raporty prognozowania przepływów pieniężnych z danymi, najpierw należy uruchomić proces obliczania prognozy za pomocą funkcji **Oblicz prognozy przepływów pieniężnych** z obszaru Zarządzanie gotówką i bankami.  Należy to zrobić dla każdej firmy uwzględnionej w prognozie.  Następnie należy odświeżyć zagregowaną miarę LedgerCovLiquidityMeasurement na stronie **Magazyn jednostek**.  

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


