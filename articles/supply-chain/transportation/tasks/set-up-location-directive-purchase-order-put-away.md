--- 
title: "Konfigurowanie dyrektywy lokalizacji dla odłożenia zamówienia zakupu"
description: "W tej procedurze pokazano sposób konfigurowania prostej dyrektywy lokalizacji."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 45e1e54c807597d4d5ff7370748012cbf28c1c6b
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>Konfigurowanie dyrektywy lokalizacji dla odłożenia zamówienia zakupu

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób konfigurowania prostej dyrektywy lokalizacji. W pokazanym przykładzie jest tworzona dyrektywa lokalizacji, która będzie używana do określenia, gdzie mają zostać odłożone towary przyjęte na podstawie zamówienia zakupu. Ten przewodnik po zadaniach można odtworzyć przy użyciu danych firmy demonstracyjnych USMF. Warunki wstępne: Należy utworzyć kod dyspozycji. W tej procedurze stosujemy kod dyspozycji o nazwie Ponowne etykietowanie. Jeśli tworzysz dyrektywę lokalizacji z własnymi danymi, musisz skonfigurować funkcje zaawansowanego zarządzania magazynem dla magazynu i towarów.  Ta procedura jest przeznaczona dla kierownika magazynu.

1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Dyrektywy lokalizacji.
2. W polu Typ zlecenia zaznacz opcję „Zamówienia zakupu”.

## <a name="create-a-location-directive-header"></a>Tworzenie nagłówka dyrektywy lokalizacji
1. Kliknij przycisk Nowy.
2. W polu Numer sekwencyjny wpisz liczbę.
    * Jest to sekwencja przetwarzania dyrektywy lokalizacji dla wybranego typu pracy. Można również zmienić taką sekwencję, jeśli trzeba.  
3. W polu Nazwa wpisz wartość.
    * Jest to unikatowy identyfikator tej dyrektywy.  
4. W polu Typ pracy zaznacz opcję „Odłożenie”.
    * Wybierz typ pracy do wykonania. W przypadku dyrektywy o typie zlecenia Zamówienie zakupu jedyną obsługiwaną wartością jest Odłożenie.  
5. W polu Oddział wpisz wartość.
6. W polu Magazyn wpisz wartość.
    * Pole Kod dyrektywy należy pozostawić puste.  Kody dyrektyw są używane do kojarzenia wiersza zlecenia typu Odłożenie z określonymi dyrektywami. Dla zamówień zakupu lokalizacja ostatniego wiersza zlecenia typu Odłożenie jest rozpoznawana przed ustaleniem szablonu pracy. Z tego względu nie można powiązać ostatniego wiersza szablonu pracy z konkretną dyrektywą.   
7. W polu Kod dyspozycji wpisz wartość.
    * Kod dyspozycji ogranicza użycie dyrektywy lokalizacji, tak że jest ona używana tylko wtedy, gdy pracownik magazynu wprowadza tę konkretną wartość podczas rejestrowania towaru za pomocą urządzenia przenośnego.  
8. Kliknij przycisk Zapisz.

## <a name="edit-the-query-for-directive"></a>Edytowanie zapytania dyrektywy
1. Kliknij opcję Edytuj kwerendę.
    * Stosowanie tej dyrektywy jest już ograniczone do towarów zarejestrowanych w określonym magazynie i z określonym kodem dyspozycji. Można dodać inne ograniczenia za pomocą zapytania.  
2. Kliknij przycisk OK.

## <a name="add-directive-lines"></a>Dodawanie wierszy dyrektywy
1. Kliknij przycisk Nowy.
    * Jest to sekwencja przetwarzania wierszy dyrektywy lokalizacji dla wybranego typu pracy. Można również zmienić taką sekwencję, jeśli trzeba.  
2. W polu Od ilości wprowadź liczbę.
    * Jest to najmniejsza ilość, dla jakiej ten wiersz dyrektywy jest prawidłowy.  
3. W polu Do ilości wprowadź liczbę.
4. W polu Jednostka wpisz wartość.
    * Jednostka, w jakiej są wyrażone wartości Od ilości i Do ilości. Jeśli to pole pozostanie puste, stosowana jest jednostka magazynowa z towaru.  
5. W polu Zlokalizuj ilość wybierz opcję.
    * Brak lub Liczba numerów identyfikacyjnych: Ilość zarejestrowana na każdym numerze identyfikacyjnym. Ilość w jednostkach: Cała ilość, jaka została zarejestrowana. Pozostała ilość: Ilość, jaka pozostała jeszcze do zarejestrowania z wiersza zamówienia zakupu. Oczekiwana ilość: Całkowita ilość, która jest określona w wierszu zamówienia zakupu.  
6. Zaznacz pole wyboru Ogranicz według jednostki lub usuń jego zaznaczenie.
    * Jeśli wybierzesz tę opcję i określisz jednostkę na stronie Ogranicz według jednostki, w lokalizacji można umieścić tylko towary o tej jednostce miary. Na przykład jeśli jednostką miary jest PL (paleta), w podanej lokalizacji można umieścić tylko towary na paletach.  
7. Zaznacz pole wyboru Zezwalaj na podział lub usuń jego zaznaczenie.
    * Umożliwia to dyrektywie dzielenie ilości na wiele lokalizacji.  
8. Kliknij przycisk Zapisz.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>Ograniczanie wiersza dyrektywy do określonej jednostki
1. Kliknij opcję Ogranicz według jednostki.
    * Ten przycisk jest dostępny tylko po naciśnięciu przycisku Zapisz po zaznaczeniu pola wyboru Ogranicz według jednostki.  
2. W polu Jednostka wpisz wartość.
3. Zamknij stronę.

## <a name="add-a-location-directive-action-line"></a>Dodawanie wiersza działania dyrektywy lokalizacji
1. Kliknij przycisk Nowy.
    * Jest to sekwencja przetwarzania wierszy działań dyrektywy lokalizacji dla wybranego typu pracy. Można również zmienić taką sekwencję, jeśli trzeba.  
2. W polu Nazwa wpisz wartość.
    * Jest to unikatowy identyfikator tego działania dyrektywy.  
3. W polu Użycie stałej lokalizacji wybierz opcję.
    * Lokalizacje stałe i niestałe: dozwolone są wszystkie lokalizacje niestałe, a także własna stała lokalizacja produktu, w zakresie określonym w zapytaniu.  Tylko stała lokalizacja dla produktu: dozwolone są stałe lokalizacje dla produktu, a wszystkie warianty produktu mają ten sam zbiór stałych lokalizacji. Tylko stałe lokalizacje dla wariantów produktu: dozwolone są tylko stałe lokalizacje określone dla każdego wariantu produktu.  
4. W polu Strategia wybierz opcję.
    * Dla zleceń typu Zamówienie zakupu są obsługiwane następujące strategie: Brak: towar jest umieszczany w pierwszej znalezionej lokalizacji. Konsolidacja: towar jest umieszczany w lokalizacji, gdzie są już dostępne podobne towary. Pusta lokalizacja bez przychodzącej pracy: towar jest umieszczany w pierwszej pustej lokalizacji, jaka zostanie znaleziona. Lokalizacja jest uważana za pustą, jeśli nie ma w niej fizycznych zapasów i nie ma żadnych oczekiwanych prac przychodzących.  
5. Kliknij przycisk Zapisz.

## <a name="edit-the-query-for-directive-action-line"></a>Edytowanie wiersza działania zapytania dyrektywy
1. Kliknij opcję Edytuj kwerendę.
2. Kliknij przycisk Dodaj.
3. W polu Pole wpisz „Identyfikator profilu lokalizacji”.
    * W tym przykładzie ograniczymy możliwe lokalizacje przy użyciu identyfikatora profilu lokalizacji.  
4. W polu Kryteria wpisz wartość.
5. Kliknij przycisk OK.
    * Można kontynuować dodawanie wierszy dyrektywy i działań dyrektywy, aż zostaną objęte wszystkie możliwe scenariusze w magazynie.  


