---
title: Generowanie dokumentu wewnętrznego przesunięcia magazynowego
description: Ta procedura pokazuje, jak utworzyć dokumenty przeniesienia w celu przesunięcia towarów wewnątrz firmy.
author: AdamTrukawka
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
ms.openlocfilehash: 27d18b30586775c98dc602215090810b0a1b918a
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337178"
---
# <a name="generate-a-transfer-document-for-an-internal-inventory-transfer"></a>Generowanie dokumentu wewnętrznego przesunięcia magazynowego

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak utworzyć dokumenty przeniesienia w celu przesunięcia towarów wewnątrz firmy. Procedura jest dostępna tylko dla firm z główną siedzibą na Litwie. Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się na Litwie. Zanim będzie można wykonać tę procedurę, należy wykonać procedurę „Konfigurowanie dokumentów przesunięcia towarów wewnątrz firmy”. Procedura jest przeznaczona dla pracowników księgujących zapasy. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


## <a name="create-a-transfer-order"></a>Tworzenie zamówienia przeniesienia
1. Wybierz kolejno opcje Zarządzanie zapasami > Zamówienia przychodzące > Zamówienie przeniesienia.
2. Kliknij przycisk Nowy.
3. W polu Z magazynu wprowadź lub wybierz wartość.
4. W polu Do magazynu wprowadź lub wybierz wartość.
5. Kliknij przycisk Dodaj.
6. Na liście oznacz wybrany wiersz.
7. W polu Numer towaru wprowadź lub wybierz wartość.

## <a name="enter-transportation-details-for-the-transfer-order"></a>Wprowadzanie szczegółów transportu dla zamówienia przeniesienia
1. Kliknij przycisk Zapisz.
2. W okienku akcji kliknij pozycję Wysyłka.
3. Kliknij opcję Szczegóły transportu.
4. W polu Drukuj szczegóły transportu zaznacz opcję Tak.
5. W polu Towary wydane przez wprowadź lub wybierz wartość.
6. W polu Opakowanie wpisz wartość.
7. W polu Poziom zagrożenia ładunku wpisz wartość.
8. Wprowadź lub wybierz wartość w polu Przewoźnik.
9. Wprowadź lub wybierz wartość w polu Model.
10. W polu Numer rejestracji wpisz wartość.
11. W polu Numer rejestracyjny przyczepy wpisz wartość.
12. Wprowadź lub wybierz wartość w polu Kierowca.
13. W polu Nazwisko kierowcy wpisz wartość.
14. Kliknij przycisk Zapisz.
15. Zamknij stronę.

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a>Wyświetlanie dokumentu dostawy dla niezaksięgowanego zamówienia przeniesienia
1. Kliknij opcję Dokument dostawy.
2. Kliknij przycisk OK.
3. Zamknij stronę.

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a>Wyświetlanie dokumentu dostawy dla zaksięgowanego zamówienia przeniesienia
1. W okienku akcji kliknij pozycję Zamówienie przeniesienia.
2. W okienku akcji kliknij pozycję Wysyłka.
3. Kliknij opcję Wyślij zamówienie przeniesienia.
4. Kliknij kartę Ogólne.
5. W polu Aktualizuj wybierz opcję.
6. Kliknij kartę Przegląd.
7. W polu Dokument dostawy wpisz wartość.
8. Kliknij przycisk OK.
9. W okienku akcji kliknij pozycję Wysyłka.
10. Kliknij opcję Dokument dostawy.
11. Kliknij przycisk OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
