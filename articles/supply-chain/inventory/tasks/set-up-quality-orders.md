---
title: Konfigurowanie zleceń kontroli jakości
description: W tej procedurze pokazano sposób włączania procesu zarządzania jakością, gdzie zapasy przychodzące muszą być kontrolowane bezpośrednio po rejestracji przyjęcia.
author: perlynne
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, InventTestTable, DefaultDashboard, InventTestVariable, InventTestVariableOutcome, InventItemSampling, InventTestQualityGroup, InventTestItemQualityGroupAdd, SysQueryForm, InventTestItemQualityGroup, InventTestGroup, InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 22cbaa2eaeaa8884a33bffc2c94b3404628ba448
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809549"
---
# <a name="set-up-quality-orders"></a>Konfigurowanie zleceń kontroli jakości

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób włączania procesu zarządzania jakością, gdzie zapasy przychodzące muszą być kontrolowane bezpośrednio po rejestracji przyjęcia. Procedurę zazwyczaj przeprowadza menedżer ds. kontroli jakości. Proces obejmuje utworzenie grupy kontroli jakości, zdefiniowanie towarów, z których mają być pobierane próbki, oraz utworzenie grupy testów, które mają być wykonywane na towarach w grupie kontroli jakości. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.


## <a name="enable-quality-management"></a>Włączanie zarządzania jakością
1. Otwórz **Okienko nawigacji > Moduły > Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem**.
2. Kliknij kartę **Zarządzanie jakością**.
3. W opcji **Korzystaj z funkcji zarządzania jakością** wybierz wartość Tak.
4. Kliknij opcję **Konfiguracja raportu**. W firmie USMF konfiguracja raportu dotyczącego zarządzania jakością jest już zdefiniowana. Jeśli tego nie zrobiono, musisz w tym miejscu dodać nowe wiersze dla różnych typów raportów, a następnie wybrać typ dokumentu, który ma być używany dla każdego raportu.  
5. Zamknij stronę.
6. Zamknij stronę.

## <a name="create-a-test"></a>Tworzenie testu
1. Wybierz kolejno opcje **Zarządzanie zapasami > Ustawienia > Kontrola jakości > Testy**.
2. Kliknij przycisk **Nowy**.
3. W polu **Test** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. W polu **Typ** wpisz „Opcja”. W tym przykładzie wybierzemy opcję „Opcja”, co umożliwi przypisywanie wyników testów na podstawie wstępnie zdefiniowanych wartości.  
6. Kliknij przycisk **Zapisz**.
7. Zamknij stronę.

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a>Tworzenie zmiennych testowych w celu zdefiniowania sposobu rejestrowania wyników testów
1. Wybierz kolejno opcje **Zarządzanie zapasami > Ustawienia > Kontrola jakości > Zmienne testowe**.
2. Kliknij przycisk **Nowy**.
3. W polu **Zmienna** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. Kliknij przycisk **Zapisz**.
6. Kliknij opcję **Wyniki**.
7. Kliknij przycisk **Nowy**.
8. W polu **Wynik** wpisz wartość.
9. W polu **Opis** wpisz wartość.
10. W polu **Stan wyniku** wybierz opcję „Sukces”.
11. Kliknij przycisk **Zapisz**.
12. Kliknij przycisk **Nowy**.
13. W polu **Wynik** wpisz wartość.
14. W polu **Opis** wpisz wartość.
15. Kliknij przycisk **Zapisz**.
16. Zamknij stronę.
17. Zamknij stronę.

## <a name="set-up-item-sampling"></a>Konfigurowanie wyrywkowej kontroli towarów
1. Wybierz kolejno opcje **Zarządzanie zapasami > Ustawienia > Kontrola jakości > Kontrola wyrywkowa pozycji**.
2. Kliknij przycisk **Nowy**.
3. W polu **Kontrola wyrywkowa** towarów wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. W polu **Wartość** wprowadź liczbę. Ta wartość odnosi się do specyfikacji ilości wybranej w sąsiednim polu.  
6. Rozwiń lub zwiń sekcję **Proces**.
7. Zaznacz lub wyczyść pole wyboru **Pełne blokowanie**. Jeśli wybierzesz tę opcję, niepowodzenie testu spowoduje zablokowanie całej partii lub ilości w wierszu zamówienia. Jeśli nie zaznaczysz opcji, będą blokowane tylko towary w zleceniu kontroli jakości.  
8. Kliknij przycisk **Zapisz**.
9. Zamknij stronę.

> [!NOTE]
> Funkcja *Zarządzania jakością dla procesów magazynowych* dodaje nowe możliwości wyrywkowej kontroli towaru. Dodaje pojęcie *Zakresu kontroli wyrywkowej towarów* i możliwość zdefiniowania pełnego numeru identyfikacyjnego jako specyfikacji ilości. Jeśli ta funkcja jest włączona, szczegóły można uzyskać w temacie [Zarządzanie jakością w procesach magazynowych](../quality-management-for-warehouses-processes.md).

## <a name="create-a-quality-group"></a>Tworzenie grupy kontroli jakości
1. Wybierz kolejno opcje **Zarządzanie zapasami > Ustawienia > Kontrola jakości > Grupy jakości**.
2. Kliknij przycisk **Nowy**.
3. W polu **Grupa jakości** wpisz wartość. Użyj nazwy opisowej, aby łatwiej identyfikować, które rodzaje towarów będzie zawierać grupa (tzn. jakich użyto kryteriów pobierania próbek).  
4. W polu **Opis** wpisz wartość.
5. Kliknij przycisk **Zapisz**.
6. Kliknij przycisk **Dodaj towary**.
7. Zaznacz wiersz **Numer towaru**. W tym przykładzie filtrowanie będzie wykonywane na podstawie kodu towaru.  
8. W polu **Kryteria** wpisz wartość. Na przykład wpisz T*, aby filtrować według kodów towarów rozpoczynających się literą T.  
9. Kliknij przycisk **OK**.
10. Kliknij przycisk **OK**.
11. Kliknij opcję **Grupy jakości towarów**.
12. Zamknij stronę.
13. Zamknij stronę.

## <a name="create-a-test-group"></a>Tworzenie grupy testowej
1. Wybierz kolejno opcje **Zarządzanie zapasami > Ustawienia > Kontrola jakości > Grupy testowe**.
2. Kliknij przycisk **Nowy**.
3. W polu **Grupa testowa** wpisz wartość. Nadaj **grupie testowej** nazwę, która pomoże Ci zapamiętać, jakiego rodzaju testy były wykonywane i z którą grupą kontroli jakości powinny być skojarzone. Jeśli na przykład grupa ma być używana do testów jakości na towarach o nazwach zaczynających się literą „T”, można nazwać grupę „Testy towarów na T”.  
4. W polu **Opis** wpisz wartość.
5. W polu **Kontrola wyrywkowa** towarów zaznacz utworzony wcześniej wiersz pobierania próbek.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Kliknij przycisk **Dodaj**.
8. W polu **Numer sekwencyjny** wpisz liczbę.
9. W polu **Test** zaznacz utworzony wcześniej test.
10. Na liście znajdź i zaznacz odpowiedni rekord.
11. Kliknij kartę **Test**.
12. W polu **Zmienna** zaznacz utworzoną wcześniej zmienną.
13. Na liście znajdź i zaznacz odpowiedni rekord.
14. W polu **Wynik domyślny** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście kliknij łącze w wybranym wierszu.
16. Kliknij przycisk **Zapisz**.
17. Zamknij stronę.

## <a name="define-when-quality-orders-will-be-created"></a>Określanie warunków tworzenia zleceń kontroli jakości
1. Wybierz kolejno opcje **Zarządzanie zapasami > Ustawienia > Kontrola jakości > Skojarzenia jakości**.
2. Kliknij przycisk **Nowy**.
3. W polu **Typ odwołania** wybierz opcję.
4. W polu **Kod towaru** zaznacz opcję „Grupa”. W tym przykładzie wybierzemy opcję „Grupa” i użyjemy grupy kontroli jakości utworzonej wcześniej. Można także zaznaczyć wartość „Tabela”, aby określić towary ręcznie, lub opcję „Wszystko”, aby dodać wszystkie towary do zlecenia kontroli jakości.  
5. W polu **Towar** wybierz utworzoną wcześniej grupę towarów. Opcje dostępne w polu Towar zależą od ustawienia w polu Kod towaru.  
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Rozwiń lub zwiń sekcję Proces.
8. W polu **Typ zdarzenia** wybierz opcję. Jest to zdarzenie wyzwalające test. Dostępne opcje zależą od procesu, który wybrano w polu Typ odwołania.  
9. W polu **Wykonanie** wybierz opcję.
10. Rozwiń lub zwiń sekcję **Przetwarzanie zlecenia** kontroli jakości.
11. W polu **Blokowanie zdarzeń** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie. To pole zawiera listę procesów, które można zablokować, jeśli zlecenie kontroli jakości jest nadal otwarte. Dostępne opcje zależą od tego, co wybrano w polu Typ zdarzenia.  
12. Na liście kliknij łącze w wybranym wierszu. Będzie to zależało od poprzednio wybranych wartości. Zaznacz tę opcję, jeśli następujące procesy mają być zablokowane przy jednoczesnym zachowaniu powiązania otwartych zleceń kontroli jakości z wierszem dokumentu źródłowego.  
13. Rozwiń lub zwiń sekcję **Specyfikacje**.
14. W polu **Grupa testowa** zaznacz utworzoną wcześniej grupę.
15. Na liście znajdź i zaznacz odpowiedni rekord.
16. Kliknij przycisk **Zapisz**.
17. Zamknij stronę.

> [!NOTE]
> Funkcja *Zarządzania jakością dla procesów magazynowych* zapewnia dodatkowe opcje konfiguracji skojarzeń jakości. Dodaje nowy warunek (**Odpowiedni typ magazynu**) i nowe ustawienie (**Zasady przetwarzania jakości**). Jeśli ta funkcja jest włączona, szczegóły można uzyskać w temacie [Zarządzanie jakością w procesach magazynowych](../quality-management-for-warehouses-processes.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]