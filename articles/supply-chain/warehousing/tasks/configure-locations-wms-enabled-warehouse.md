--- 
title: "Konfigurowanie lokalizacji w magazynie z obsługą WMS"
description: "W tym przewodniku pokazano, jak skonfigurować lokalizację dla nowego magazynu obsługującego WMS (magazynu, który używa zaawansowanych procesów zarządzania magazynem)."
author: perlynne
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
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 044da854273345877be92c9eab787f4edf0bba5b
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a>Konfigurowanie lokalizacji w magazynie z obsługą WMS

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku pokazano, jak skonfigurować lokalizację dla nowego magazynu obsługującego WMS (magazynu, który używa zaawansowanych procesów zarządzania magazynem). Ten proces jest zwykle wykonywany przez kierownika magazynu. Można wykonać zadania z tego przewodnika przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Warunkiem wstępnym jest posiadanie co najmniej jednego skonfigurowanego oddziału.


## <a name="create-a-new-warehouse"></a>Tworzenie nowego magazynu
1. Przejdź do okna Magazyny.
2. Kliknij przycisk Nowy.
3. W polu Magazyn wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Oddział wpisz wartość.
6. Rozwiń lub zwiń sekcję Magazyn.
7. W opcji Użyj procesów zarządzania magazynami zaznacz wartość Tak.
    * To ustawienie pozwala uruchomiać zaawansowane procesy magazynowe przy użyciu pracy magazynowej i urządzeń przenośnych.  
8. Zamknij stronę.

## <a name="define-a-location-format"></a>Definiowanie formatu lokalizacji
1. Przejdź do okna Formaty lokalizacji.
    * Formaty lokalizacji to system nazewnictwa używany do tworzenia unikatowych i spójnych nazw dla różnych pozycji pojemników w lokalizacji używanych w magazynie. Może być korzystne używanie separatorów jako elementu formatu lokalizacji, aby ułatwić identyfikowanie składników lokalizacji, takich jak numer alei. W tym przykładzie utworzymy nazwę z czterema składnikami. Mogą to być na przykład korytarz, regał, półka i pojemnik.  
2. Kliknij przycisk Nowy.
3. W polu Format lokalizacji wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Opis segmentu wpisz wartość.
    * Opisuje to, co reprezentuje pierwsza część nazwy lokalizacji. Na przykład może to być korytarz.  
6. W polu Długość wpisz liczbę.
    * Określa, ile znaków musi mieć ta część nazwy lokalizacji. Należy zwrócić uwagę, że suma liczby znaków we wszystkich składnikach nazwy, łącznie z separatorami, nie może przekroczyć 10.  
7. W polu Separator wpisz wartość.
    * Określa, który znak lub symbol jest używany między pierwszym a drugim składnikiem nazwy.  
8. Kliknij przycisk Nowy.
9. W polu Opis segmentu wpisz wartość.
10. W polu Długość wpisz liczbę.
11. W polu Separator wpisz wartość.
12. Kliknij przycisk Nowy.
13. W polu Opis segmentu wpisz wartość.
14. W polu Długość wpisz liczbę.
15. W polu Separator wpisz wartość.
16. Kliknij przycisk Nowy.
17. W polu Opis segmentu wpisz wartość.
18. W polu Długość wpisz liczbę.
19. Kliknij przycisk Zapisz.
20. Zamknij stronę.

## <a name="define-location-types"></a>Definiowanie typów lokalizacji
1. Przejdź do okna Typy lokalizacji.
    * Typy lokalizacji mogą służyć jako opcje filtrowania do kontrolowania różnych procesów zarządzania magazynem. Jako minimum należy utworzyć pośrednie i docelowe typy lokalizacji wysyłki w celu zdefiniowania procesu zarządzania wysyłkami z magazynu.  
2. Kliknij przycisk Nowy.
3. W polu Typ lokalizacji wpisz wartość.
4. Wypełnij pole Opis.
5. Zamknij stronę.

## <a name="define-location-profile"></a>Definiowanie profilu lokalizacji
1. Przejdź do okna Profile lokalizacji.
    * Zdefiniowanie profili lokalizacji jest bardzo ważne. W tym miejscu można kontrolować pojemność zgrupowanych lokalizacji oraz zasady dotyczących tego, które zapasy i jak są przechowywane. Profile lokalizacji mogą służyć jako opcje filtrowania do kontrolowania różnych procesów zarządzania magazynem. Jako minimum należy utworzyć profil lokalizacji użytkownika w celu umożliwienia procesów zarządzania magazynem.  
2. Kliknij przycisk Nowy.
3. W polu Identyfikator profilu lokalizacji wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Format lokalizacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Typ lokalizacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Na liście kliknij łącze w wybranym wierszu.
11. Zaznacz lub wyczyść pole wyboru Pozwól na mieszane stany zapasów.
    * Włącz tę opcję, aby zezwalać na mieszane wartości stanu zapasów w lokalizacjach, które mają być grupowane w tym profilu lokalizacji.  
12. Zaznacz lub wyczyść pole wyboru Zastąp reguły dla dni partii.
    * Włącz tę opcję, aby zastąpić regułę dopuszczalnej liczby dni różnicy daty ważności partii zapasów i umożliwić mieszanie partii zapasów, które nie przestrzegają tej reguły.  
13. Zaznacz lub wyczyść pole wyboru Pozwól na inwentaryzację ciągłą.
    * Włącz tę opcję, aby zezwolić na inwentaryzację ciągłą we wszystkich lokalizacjach, które mają być grupowane w tym profilu lokalizacji.  
14. Rozwiń lub zwiń sekcję Wymiary.
    * Karta Wymiary umożliwia zdefiniowanie parametrów oraz metod w celu umożliwienia dokładnego obliczania obciążenia pojemności w każdej lokalizacji.  
15. Zamknij stronę.

## <a name="enable-warehouse-management-parameters"></a>Włączanie parametrów zarządzania magazynem
1. Przejdź do okna Parametry zarządzania magazynem.
    * Aby móc wykonywać prace magazynowe, należy ustawić parametry profilu lokalizacji użytkownika dla lokalizacji pośredniej i lokalizacji końcowej wysyłki. Z chwilą zakończenia procesu wysyłki w lokalizacji końcowej wysyłki o zdefiniowanym typie powiązane transakcje wysyłki zostaną zaktualizowane stanu „Pobrane”.  
2. Rozwiń lub zwiń sekcję Profile lokalizacji.
3. W polu Lokalizacja użytkownika kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście kliknij łącze w wybranym wierszu.
5. Rozwiń lub zwiń sekcję Typy lokalizacji.
6. W polu Typ lokalizacji pośredniej kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Typ lokalizacja końcowej wysyłki kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście kliknij łącze w wybranym wierszu.
10. Zamknij stronę.

## <a name="define-warehouse-zone-groups"></a>Definiowanie grup stref magazynowych
1. Przejdź do okna Grupy stref magazynowych.
    * Strefy magazynowe mogą służyć jako filtry opcji do kontrolowania różnych procesów zarządzania magazynem. Aby można było zdefiniować strefę, należy utworzyć grupę stref.  
2. Kliknij przycisk Nowy.
3. W polu Identyfikator grupy strefy wpisz wartość.
4. W polu Nazwa grupy strefy wpisz wartość.
5. Zamknij stronę.

## <a name="define-warehouse-zones"></a>Definiowanie strefy magazynowych
1. Przejdź do okna Strefy.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator strefy wpisz wartość.
4. W polu Nazwa strefy wpisz wartość.
5. W polu Identyfikator grupy strefy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. Zamknij stronę.

## <a name="create-locations-using-the-location-setup-wizard"></a>Tworzenie lokalizacji za pomocą Kreatora konfiguracji lokalizacji
1. Przejdź do okna Kreator konfiguracji lokalizacji.
2. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu Identyfikator strefy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Identyfikator profilu lokalizacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Na liście kliknij łącze w wybranym wierszu.
11. Na liście oznacz wybrany wiersz.
12. W polu Numer początkowy wpisz liczbę.
    * Wartości w polach Numer początkowy i Numer końcowy określają, ile lokalizacji zostanie utworzonych. Na przykład jeśli ustawisz Numer początkowy na 1, a Numer końcowy na 3 dla wszystkich czterech wierszy w formacie lokalizacji, zostanie utworzonych 81 lokalizacji (3x3x3x3).  
13. W polu Numer końcowy wpisz liczbę.
14. Na liście znajdź i zaznacz odpowiedni rekord.
15. W polu Numer początkowy wpisz liczbę.
16. W polu Numer końcowy wpisz liczbę.
17. Na liście znajdź i zaznacz odpowiedni rekord.
18. W polu Numer początkowy wpisz liczbę.
19. W polu Numer końcowy wpisz liczbę.
20. Na liście znajdź i zaznacz odpowiedni rekord.
21. W polu Numer początkowy wpisz liczbę.
22. W polu Numer końcowy wpisz liczbę.
23. Kliknij przycisk Utwórz.

## <a name="create-locations-manually"></a>Ręczne tworzenie lokalizacji
1. Przejdź do okna Lokalizacje.
    * Można łatwo ręcznie tworzyć lokalizacje w magazynie. Nazwa lokalizacji i identyfikator profilu lokalizacji są wartościami wymaganymi.  
2. Kliknij przycisk Nowy.
3. W polu Magazyn wpisz wartość.
4. W polu Lokalizacja wpisz wartość.
    * Należy zauważyć, że tworzysz tutaj nową lokalizację, więc należy wpisać nową unikatową nazwę zamiast wybierać już istniejącą.  
5. W polu Identyfikator profilu lokalizacji wpisz wartość.
6. Zamknij stronę.

## <a name="define-pack-size-categories"></a>Definiowanie kategorii wielkości pakunków
1. Przejdź do okna Kategorie wielkości pakunków.
    * Kategorie wielkości pakunków mogą służyć do grupowania towarów o podobnych fizycznie rozmiarach opakowań. W tym przykładzie kategoria wielkości pakunków posłuży do sterowania pojemnością w lokalizacjach pobrania w określonej strefie magazynu. Należy zauważyć, że najpierw należy przypisać identyfikator kategorii wielkości pakunków do jednostki zwalnianego produktu, aby umożliwić używanie kategorii w ramach przetwarzania limitów składowania.  
2. Kliknij przycisk Nowy.
3. W polu Identyfikator kategorii wielkości pakunków wpisz wartość.
4. W polu Nazwa kategorii wielkości pakunków wpisz wartość.
5. Zamknij stronę.

## <a name="define-location-stocking-limits"></a>Określ limity składowania w lokalizacji
1. Przejdź do okna Limity składowania w lokalizacji.
    * Limity składowania w lokalizacji pomagają się upewnić, że nie jest tworzone żądanie umieszczenia zapasów w lokalizacji, która nie ma fizycznej pojemności do zmieszczenia tych zapasów.  
2. Kliknij przycisk Nowy.
3. W polu Magazyn wpisz wartość.
4. W polu Identyfikator profilu lokalizacji wpisz wartość.
5. W polu Identyfikator kategorii wielkości pakunków wpisz wartość.
6. Wprowadź liczbę w polu Ilość.
7. Kliknij przycisk Zapisz.
8. Zamknij stronę.

## <a name="define-fixed-picking-locations"></a>Definiowanie stałych lokalizacji pobrania
1. Przejdź do okna Stałe lokalizacje.
    * Lokalizacje, które mają być używane, można określić dla każdego produktu lub dla wariantu produktu. Istnieje możliwość utworzenia wielu stałych lokalizacji dla tego samego produktu w tym samym magazynie.  
2. Kliknij przycisk Nowy.
3. W polu Numer towaru wpisz wartość.
4. W polu Magazyn wpisz wartość.
5. W polu Lokalizacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście kliknij łącze w wybranym wierszu.
7. Zamknij stronę.


