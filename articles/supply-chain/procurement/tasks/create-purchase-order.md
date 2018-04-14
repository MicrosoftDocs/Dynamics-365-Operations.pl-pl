--- 
title: "Tworzenie zamówienia zakupu"
description: "W tej procedurze pokazano sposób ręcznego tworzenia zamówienia sprzedaży."
author: FrankDahl
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 27ed15e6d9a376c4203e5446d056f221bd3eb730
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób ręcznego tworzenia zamówienia sprzedaży. Najczęściej zamówienia zakupu są tworzone automatycznie jako rezultat planowania głównego, dostawy bezpośredniej i innych procesów. W przypadku tworzenia ręcznego najczęściej robi to pracownik działu zakupów. W pokazanym tutaj przykładzie można użyć firmy demonstracyjnych USMF, podstawiając wartości sugerowane w notatkach do poszczególnych kroków.


## <a name="create-the-purchase-order-header"></a>Tworzenie nagłówka zamówienia zakupu
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. Wybierz konto dostawcy US-101.
    * Kiedy wybierzesz dostawcę, szczegóły z jego rekordu, takie jak adres, konto płatnika, warunki dostawy i metoda dostawy, zostaną skopiowane jako wartości domyślne do nagłówka zamówienia. Wartości te można zmienić w dowolnym momencie.  
4. Rozwiń sekcję Ogólne.
    * Pole Oddział wraz z polem Magazyn określa, dokąd należy dostarczyć kupowane towary lub usługi. Domyślnym adresem dostawy jest oddział. Oba pola mogą być wypełnione wartościami skonfigurowanymi dla wybranego dostawcy lub można je określić ręcznie.  
    * Pole Data dostawy jest używane do określenia, kiedy kupione towary i usługi muszą zostać dostarczone. Można określić jedną datę dostawy dla całego zamówienia lub unikatowe daty dostawy dla poszczególnych wierszy zamówienia. Jeśli data dostawy określona w tym polu nie może zostać dotrzymana dla określonych produktów lub usług, ponieważ mają one dłuższe czasy realizacji, te wiersze zostaną utworzone z odpowiednimi późniejszymi datami dostawy.  
5. Zwiń sekcję Ogólne.
6. Rozwiń sekcję Administracja.
    * Pole Zamawiający może służyć do określania, kto składa zamówienie. Może być wygodne udostępnienie tej informacji dostawcy w przypadku, gdy musi się on skontaktować z tą osobą. Wartość w polu może być przypisywana automatycznie, jeśli konto bieżącego użytkownika jest skojarzone z nazwą na stronie Użytkownicy.  
7. Zwiń sekcję Administracja.
8. Kliknij przycisk OK.
    * Został utworzony nagłówek zamówienia. Podczas pracy z wierszami zamówienia zakupu jest wyświetlane tylko podsumowanie informacji nagłówka. Aby wyświetlić pozostałe informacje, kliknij nagłówek.  

## <a name="add-a-purchase-order-line"></a>Dodawanie wiersza zamówienia zakupu
1. Kliknij opcję Wiersz zamówienia zakupu.
2. Kliknij opcję Wymiary.
    * Produkty mogą być w wariantach zróżnicowanych według wymiarów, takich jak kolor, rozmiar lub styl. Produkty mogą być również skonfigurowane do używania wymiarów magazynowania, takich jak oddział i magazyn. Istnieją również opcjonalne wymiary śledzenia, takie jak numery partii i numery seryjne. Aby zwiększyć efektywność wprowadzania zamówień, można dodać pola często używanych wymiarów bezpośrednio do siatki zamówień.  
3. Zaznacz pole wyboru Kolor.
    * Opcjonalnie: Jeśli zaznaczysz pole Zapisz ustawienia, przy następnym otwarciu strony zamówienia zakupu wybrane wymiary będą wyświetlane również w siatce wierszy zamówienia.  
4. Kliknij przycisk OK.
5. W polu Numer pozycji wybierz wartość T0004.
    * Wiersze zamówienia są tworzone dla produktów i usług przez określenie numeru towaru lub jako koszty przez określenie kategorii zaopatrzenia.  
    * Pole Kategoria zaopatrzenia służy do dodawania wierszy, gdzie kupowane towary są zaliczane w koszty bezpośrednio, a nie kierowane do zapasów. Oznacza to, że jeśli trzeba zaliczyć zamówienie zakupu w koszty, można to zrobić przez utworzenie wiersza zamówienia zakupu określającego kategorię zaopatrzenia zamiast przez tworzenie wiersza z numerem towaru. Towary mogą być także skojarzone z kategorią zaopatrzenia i w takim przypadku kategoria zaopatrzenia jest wyświetlana tylko informacyjnie.  
6. W polu Kolor wprowadź lub wybierz wartość.
    * Pola Oddział i Magazynu zazwyczaj są wypełniane wartościami z nagłówka zamówienia, ale można zastąpić te wartości, jeśli pozycje niektórych wierszy muszą zostać dostarczone do innych lokalizacji.  
7. Wprowadź liczbę w polu Ilość.
    * Zaznacz ilość, jaką chcesz kupić. W polu Ilość jest automatycznie wpisywana minimalna ilość zamówienia na produkt, jeśli ją skonfigurowano, lub wartość 1.  
    * Pole Jednostka wskazuje jednostkę miary zamówionej ilości. Zazwyczaj jednostka jest wprowadzana automatycznie na podstawie jednostki zakupu z danych głównych produktu, ale można ją zmienić.  
    * Pole Cena jednostkowa zazwyczaj zawiera wartości z umowy zakupu lub umowy handlowej. Istnieje możliwość zmiany ceny jednostkowej w poszczególnych wierszach zamówienia, na przykład jeśli specjalna cena została wynegocjowana z dostawcą.  
    * Pole Rabat zawiera kwotę rabatu na jednostkę. O ten rabat jest pomniejszana cena jednostkowa. Rabat zazwyczaj jest wstawiany automatycznie z umów zakupu lub umów handlowych, ale istnieje możliwość ręcznego zastąpienia wartości w poszczególnych wierszach, jeżeli wynegocjowano z dostawcą inne rabaty.  
    * Można wprowadzić procent rabatu, który zmniejsza kwotę netto w wierszu. Procent rabat zazwyczaj jest często automatycznie z umów zakupu lub umów handlowych, ale istnieje możliwość ręcznego zastąpienia wartości w poszczególnych wierszach, jeżeli wynegocjowano z dostawcą inny procent rabatu.  
    * Wartość w polu Kwota netto jest obliczana na podstawie innych pól wiesza, w tym ilości, ceny jednostkowej, rabatu i procentu rabatu. Istnieje możliwość zmiany kwoty netto, ale wtedy pola Cena jednostkowa, Rabat i Procent rabatu będą puste, a podczas księgowania względem wiersza zaksięgowana kwota będzie proporcjonalna do kwoty netto. Zwykle do wyświetlania kwoty netto w wierszu jest używane pole Kwota netto.  
8. Rozwiń sekcję Szczegóły wiersza.
9. Kliknij kartę Dostawa.
    * Do każdego wiersza zamówienia można przypisać unikatową datę dostawy. Data jest dziedziczona z pola w nagłówku zamówienia zakupu, ale można ją zmienić.  
10. Zwiń sekcję Szczegóły wiersza.

## <a name="review-order-totals"></a>Przegląd sum zamówienia
1. Kliknij przycisk Sumy.
    * Jeśli nie widać akcji Sumy, na pasku akcji kliknij kartę Zamówienie zakupu.  
    * To okno dialogowe pokazuje sumy dla całego zamówienia.  
    * Pole Wybór umożliwia zmianę podstawy obliczania sum. Na przykład można wybrać opcję Ilość z dokumentu przyjęcia produktów, aby pokazać sumy odnoszące się do przetworzonych ilości produktów, lub opcję Ilość zamówiona, aby pokazać zamówioną ilość produktu.  
2. Kliknij przycisk OK.


