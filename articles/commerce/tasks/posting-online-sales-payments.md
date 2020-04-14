---
title: Księgowanie sprzedaży i płatności online
description: Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3bac0cab764436a618fa570901c84ab720dbc86
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140791"
---
# <a name="posting-of-online-sales-and-payments"></a>Księgowanie sprzedaży i płatności online

[!include [banner](../includes/banner.md)]

Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym.

Księgowanie sprzedaży i płatności online jest procesem dwuetapowym.

- Ściąganie danych transakcji sprzedaży w trybie online w HQ.
- Synchronizowanie zamówień w celu utworzenia zamówień sprzedaży w HQ.

Dane transakcji w trybie online można ściągnąć, ręcznie uruchamiając zadanie P lub tworząc cykliczne zadanie wsadowe.

### <a name="manually-running-the-p-job"></a>Ręczne uruchamianie zadania P

1. Wybierz kolejno opcje Wszystkie obszary robocze > Składniki IT w handlu detalicznym i innym.
2. Kliknij Harmonogram dystrybucji.
3. Wybierz P-0001.
4. W razie potrzeby skoryguj grupy baz danych kanału.
5. Kliknij przycisk Uruchom teraz.
6. Kliknij przycisk Tak.

### <a name="scheduling-a-recurring-p-job"></a>Planowanie cyklicznego zadania P

1. Wybierz kolejno opcje Wszystkie obszary robocze > Składniki IT w handlu detalicznym i innym.
2. Kliknij Harmonogram dystrybucji.
3. Wybierz P-0001.
4. Kliknij Utwórz zadanie wsadowe.
5. Kliknij Uruchom w tle.
5. Włącz Przetwarzanie wsadowe.
6. Kliknij przycisk Cykl.
7. Wybierz opcję Brak daty zakończenia.
8. W polu Liczba wprowadź interwał między uruchomieniami w minutach. Zwykle jest to 5-10.
9. Kliknij przycisk OK.
10. Kliknij przycisk OK.

Zamówienia można synchronizować ręcznie, uruchamiając zadanie „Synchronizuj zamówienia” lub tworząc cykliczne zadanie wsadowe.

### <a name="manually-running-order-synchronization"></a>Ręcznie uruchomiona synchronizacja zamówień 

Wykonaj poniższe kroki, aby ręcznie uruchomić zadanie „Synchronizuj zamówienia” raz.

1. Wybierz kolejno opcje Wszystkie obszary robocze > Finanse sklepu.
2. Kliknij opcję Synchronizuj zamówienia.
3. W polu Hierarchia organizacyjna wybierz opcję „Sklepy według regionów”.
    * Wybierz określony sklep internetowy albo węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.  
    * Kliknij strzałkę, aby dodać zaznaczone obiekty.  
4. Kliknij kartę Uruchom w tle.
5. Wyłącz Przetwarzanie wsadowe
6. Kliknij przycisk Cykl.
7. Wybierz opcję koniec po
8. W polu Koniec po wpisz 1.
9. Kliknij przycisk OK.
10. Kliknij przycisk OK.

### <a name="scheduling-recurring-order-synchronization"></a>Planowanie synchronizacji zamówień cyklicznych

Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Wszystkie obszary robocze > Finanse sklepu.
2. Kliknij opcję Synchronizuj zamówienia.
3. W polu Hierarchia organizacyjna wybierz opcję „Sklepy według regionów”.
    * Wybierz określony sklep internetowy albo węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.  
    * Kliknij strzałkę, aby dodać zaznaczone obiekty.  
4. Kliknij kartę Uruchom w tle.
5. Włącz Przetwarzanie wsadowe
6. Kliknij przycisk Cykl.
7. Wybierz opcję Brak daty zakończenia.
8. W polu Liczba wprowadź interwał między uruchomieniami w minutach. Zwykle jest to 2-20.
9. Kliknij przycisk OK.
10. Kliknij przycisk OK.

## <a name="data-entities-involved-in-the-process"></a>Jednostki danych uczestniczące w procesie

- RetailTransactionTable
- RetailTransactionAddressTrans
- RetailTransactionInfocodeTrans
- RetailTransactionTaxTrans
- RetailTransactionSalesTrans
- RetailTransactionTaxMeasure
- RetailTransactionDiscountTrans
- RetailTransactionTaxTransGTE
- RetailTransactionMarkupTrans
- RetailTransactionPaymentTrans
- RetailTransactionAttributeTrans
