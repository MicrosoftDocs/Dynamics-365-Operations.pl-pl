---
title: "Konfigurowanie wymagań wstępnych zarządzania"
description: "Ta procedura umożliwia aktywowanie procesów zarządzania brakiem zgodności."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4bb4af7cb7aff101a8b9e6162823515f63b12886
ms.openlocfilehash: 9b5b05a3c00f093066a2714964bb99146427c3bc
ms.contentlocale: pl-pl
ms.lasthandoff: 11/02/2017

---
# <a name="set-up-prerequisites-for-management"></a>Konfigurowanie wymagań wstępnych zarządzania

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura umożliwia aktywowanie procesów zarządzania brakiem zgodności. Brak zgodności opisuje procedurę lub towar, który ma problem z jakością, gdzie opisowe informacje zawierają źródło i typ problemu. Procedura wykorzystuje dane firmy demonstracyjnej USMF. Ta procedura jest zwykle wykonywana przez kierownika ds. jakości.


## <a name="enable-quality-management-processes-within-the-company"></a>Włączanie procesów zarządzania jakością w firmie
1. Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem.
2. Kliknij kartę Zarządzanie jakością.
3. W polu Korzystaj z funkcji zarządzania jakością zaznacz opcję Tak.
    * Zaznacz ten parametr, aby umożliwić procesy zarządzania jakością w firmie.  
4. W polu Stawka godzinowa wpisz liczbę.
    * W polu Stawka godzinowa wpisz stawkę godzinową za pracę w walucie lokalnej. Stawka godzinowa używana jest do obliczania kosztów operacji związanych z niezgodnością. Stawka godzinowa i obliczone koszty stanowią odnośnikowe informacje o niezgodności i nie mają styczności z innymi funkcjami.  
5. Kliknij opcję Konfiguracja raportu.
    * Na tej stronie można określić typy uwag do raportów z kontroli jakości, które będą używane w różnych rodzajach raportów o zarządzaniu jakością.  
6. Zamknij stronę.
7. Zamknij stronę.

## <a name="enable-user-for-nonconformance-processing"></a>Włączanie użytkownika dla przetwarzania braku zgodności
1. Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.
    * Aby wykonać zatwierdzenie braku zgodności, użytkownik, który zatwierdza lub odrzuca brak zgodności, musi mieć przypisaną wartość „Nazwa” na stronie Użytkownicy. Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika.  
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Nazwa z wartością „Ricardo”.
    * Użyj filtru, aby znaleźć użytkownika, który będzie zatwierdzał lub odrzucał rekordy braku zgodności.  
3. Na liście kliknij łącze w wybranym wierszu.
    * Aby wykonać zatwierdzenie braku zgodności, upewnij się, że użytkownik, który zatwierdza lub odrzuca niezgodności, ma przypisaną wartość „Nazwa” na stronie Użytkownicy.  
4. Kliknij opcję Opcje użytkownika.
5. Kliknij kartę Preferencje.
6. W polu Włącz obsługę dokumentów zaznacz opcję Tak.
    * Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika.  
7. Zamknij stronę.
8. Zamknij stronę.
9. Zamknij stronę.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Definiowanie typów diagnostyki dla przetwarzania braku zgodności
1. Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Typy diagnostyki.
    * Na stronie Typy diagnostyki zdefiniuj klasyfikację akcji diagnostycznych. Korekta określa typ akcji diagnostycznej, którą należy wykonać dla zatwierdzonej niezgodności, osobę mającą wykonać tę akcję oraz żądaną i planowaną datę wykonania.  
2. Kliknij przycisk Nowy.
3. W polu Diagnostyka wpisz wartość.
4. Wypełnij pole Opis.
5. Zamknij stronę.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Definiowanie opłat związanych z kontrolą jakości dla przetwarzania braku zgodności
1. Wybierz kolejno opcje Zarządzanie zapasami > ustawienia > Zarządzanie jakością > Opłaty związane z kontrolą jakości.
    * Strona Opłaty związane z kontrolą jakości służy do definiowania klasyfikacji opłat, które będą używane w operacjach związanych z brakiem zgodności.  
2. Kliknij przycisk Nowy.
3. W polu Kod opłat wpisz wartość.
4. Wypełnij pole Opis.
5. Zamknij stronę.

## <a name="define-the-operations-for-nonconformance-processing"></a>Definiowanie operacji przetwarzania braku zgodności
1. Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Operacje.
    * Za pomocą strony Operacje zdefiniuj klasyfikację pracy, którą można wykonać dla zatwierdzonego braku zgodności. Podczas kojarzenia operacji z brakiem zgodności można zdefiniować szczegółowe informacje o powiązanych materiałach, godzinach robocizny i opłatach dodatkowych wymaganych do wykonania operacji. Te informacje stanowią podstawę do obliczenia szacowanego kosztu wykonania operacji.  
2. Kliknij przycisk Nowy.
3. W polu Operacje wpisz wartość.
4. Wypełnij pole Opis.
5. Zamknij stronę.

## <a name="define-problem-types-for-nonconformance-processing"></a>Definiowanie typów problemów dla przetwarzania braku zgodności
1. Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Typy problemów.
    * Użyj strony Typ problemu do zdefiniowania klasyfikacji problemów z jakością, które występują w różnych typach braku zgodności. Istnieją następujące typy braku zgodności: Wewnętrzny, Odbiorca, Dostawca, Żądanie usługi, Produkcja i Wytwarzanie produktu towarzyszącego. Jeden typ problemu można skojarzyć z wieloma typami braku zgodności.  
2. Kliknij przycisk Nowy.
3. W polu Typ problemu wpisz wartość.
4. Wypełnij pole Opis.
5. Kliknij opcję Typy niezgodności.
    * Użyj strony Typy niezgodności w celu autoryzowania użycia typu problemu dla jednego lub więcej typów braku zgodności. Na przykład typ problemu związany z kodem wady może dotyczyć wszystkich typów niezgodności, podczas gdy typ problemu związany ze skargami odbiorców może dotyczyć tylko niezgodności typu odbiorca i zlecenie serwisowe.  
6. Kliknij przycisk Nowy.
7. Na liście oznacz wybrany wiersz.
8. W polu Typ niezgodności wybierz opcję.
9. Zamknij stronę.
10. Zamknij stronę.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Definiowanie stref kwarantanny dla przetwarzania braku zgodności
1. Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Strefy kwarantanny.
2. Kliknij przycisk Nowy.
3. W polu Strefa kwarantanny wpisz wartość.
4. Wypełnij pole Opis.
5. Zamknij stronę.

