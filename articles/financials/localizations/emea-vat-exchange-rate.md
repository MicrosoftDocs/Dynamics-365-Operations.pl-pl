---
title: Podstawowe informacje o kursie wymiany dla podatku VAT
description: Ten temat zawiera informacje dotyczące kursów wymiany dla obliczania podatku VAT. Kurs wymiany używany do obliczania podatku VAT może się różnić od kursu wymiany używanego w funkcjach księgowania w firmie. Po zaksięgowaniu dokumentu w walucie obcej wszelkie występujące różnice kursowe są księgowane na określonych kontach księgowych.
author: ShylaThompson
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ExchangeRateCurrencyPairCalculationRules, LedgerParameters, SalesTaxExchangeRateType, TaxTmpWorkTrans
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 272703
ms.assetid: 2d1fad67-8234-49cc-b009-0f3cc29f5886
ms.search.region: Czech Republic, Hungary, Poland
ms.author: mrolecki
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 7e23581c73c3eb62e21dc3a53b5730c7c7cb0e62
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852332"
---
# <a name="vat-exchange-rate-overview"></a>Podstawowe informacje o kursie wymiany dla podatku VAT

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące kursów wymiany dla obliczania podatku VAT. Kurs wymiany używany do obliczania podatku VAT może się różnić od kursu wymiany używanego w funkcjach księgowania w firmie. Po zaksięgowaniu dokumentu w walucie obcej wszelkie występujące różnice kursowe są księgowane na określonych kontach księgowych.

Organizacja może wybrać kurs wymiany, który służy do obliczania podatku od towarów i usług (VAT) dla deklaracji VAT. Ten kurs wymiany może się różnić od kursu wymiany używanego w funkcjach księgowania w firmie. Funkcje księgowania obejmują m.in. przygotowywanie następujących dokumentów związanych z podatkami:

-   Faktury
-   Faktury niezależne
-   Zamówienia zakupu
-   Faktury projektu
-   Faktury korygujące
-   Faktury korygujące

Po zaksięgowaniu dokumentu w walucie obcej wszelkie występujące różnice kursowe są księgowane na określonych kontach księgowych.

## <a name="prerequisites"></a>Wymagania wstępne

Aby korzystać z ten funkcjonalności, należy odpowiednio skonfigurować system.

1.  Utwórz typy kursów wymiany i ustaw kursy wymiany dla podatku w oknie **Księga główna** &gt; **Waluty** &gt; **Typy kursu wymiany**. Można zdefiniować dowolną liczbę typów kursu wymiany i dowolną liczbę kursów wymiany dla par walut.
2.  Włącz obliczanie kursów wymiany dla podatku VAT, włączając parametr **Kurs banku** oraz definiując typy kursów wymiany dla podatków naliczonego i należnego w oknie **Księga główna** &gt; **Ustawienia księgi** &gt; **Parametry księgi głównej**.
3.  Skonfiguruj typy kursów wymiany walut dla określonych typów transakcji sprzedaży i zakupu w oknie **Księga główna** &gt; **Waluty** &gt; **Typy kursów wymiany walut dla podatku**.
4.  Skonfiguruj konta różnic podatków naliczonego i należnego oraz konta przeciwstawne tych różnic w grupach księgowania w księdze w oknie **Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Grupy księgowania**.
5.  Opcjonalnie: Skonfiguruj regułę obliczania kursu wymiany dla pary walut w oknie **Księga główna** &gt; **Waluty** &gt; **Zasady obliczania kursu wymiany dla par walut**. Zasady obliczania kursu wymiany są używane do przeliczania kwot podatku VAT na fakturach sprzedaży w walucie obcej na kwoty podatku VAT w walucie docelowej.

## <a name="overview"></a>Przegląd

Jeśli po skonfigurowaniu w systemie używania kursów wymiany dla podatku VAT trzeba wprowadzić dokument lub utworzyć zamówienie wykorzystujące walutę obcą, można użyć strony **Transakcje podatkowe**, aby ustawić wartość **Data rejestru VAT**, która będzie powodowała pobieranie i ustawianie domyślnej wartości **Kurs wymiany podatku**. Oba pola można edytować. Można również użyć pola **Podstawa po korekcie (kurs wymiany dla podatku VAT)** lub **Skorygowana kwota podatku (kurs wymiany dla podatku VAT)**, aby wprowadzić rzeczywiste kwoty podatku VAT w walucie lokalnej określonej w dokumencie zewnętrznym. Przeglądając zapisy rachunkowe, można wyświetlać różnice kwot podatku na stronie **Arkusz księgi podrzędnej**. Gdy dokument jest księgowany, dla transakcji księgowanych na skonfigurowanych przez Ciebie kontach księgi głównej możesz przeglądać wszelkie różnice w kwotach podatku spowodowane różnicami między kursem wymiany waluty dla podatku VAT a kursem wymiany waluty rozliczeniowej używanej w organizacji.




