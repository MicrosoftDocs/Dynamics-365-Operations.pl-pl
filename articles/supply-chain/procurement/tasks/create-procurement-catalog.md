--- 
title: Tworzenie katalogu zaopatrzenia
description: "W tym przewodniku pokazano sposób tworzenia katalogu zaopatrzenia."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: df844ba3834972441daa61899294b3e95cac96c1
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-procurement-catalog"></a>Tworzenie katalogu zaopatrzenia

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku pokazano sposób tworzenia katalogu zaopatrzenia. To zadanie jest zazwyczaj wykonywane przez pracownika działu zaopatrzenia. Dowiedz się także, jak pracownicy mogą używać katalogu podczas tworzenia zapotrzebowania. Aby można było utworzyć katalogu, w systemie musi istnieć hierarchia kategorii zaopatrzenia. Hierarchia, wraz ze wszystkimi znajdującymi się w niej produktami, jest dziedziczona przez nowy katalog. Można użyć tego przewodnika z danymi firmy demonstracyjne USMF, gdzie hierarchia kategorii zaopatrzenia jest już dostępna, oraz wobec przykładów opisanych w krokach procedury.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Sprawdzanie, czy istnieje hierarchia kategorii zaopatrzenia
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Kategorie zaopatrzenia.
    * W danych firmy demonstracyjnej USMF jest dostępna hierarchia kategorii zaopatrzenia, a produkty zostały dodane do kategorii Urządzenia biurowe/Komputery. Jeśli wykonujesz tę procedurę jako przewodnik po zadaniu, musisz odblokować przewodnik, aby móc przeglądać kategorię. Jeśli hierarchia nie była dostępna, należało ją utworzyć kliknięciem przycisku Nowy. Można to zrobić tylko raz.  
2. Zamknij stronę.

## <a name="create-a-catalog"></a>Tworzenie katalogu
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Katalogi > Katalogi zaopatrzenia.
2. Kliknij przycisk Nowy katalog zaopatrzenia, aby otworzyć rozwijane okno dialogowe.
3. W polu Nazwa wpisz wartość.
4. Kliknij przycisk OK.
5. W drzewie rozwiń węzeł „KATEGORIE ZAOPATRZENIA W FIRMIE”.
6. W drzewie rozwiń węzeł „URZĄDZENIA BIUROWE”.
7. W drzewie zaznacz pozycję „Komputery”.
    * Produkty z kategorii zaopatrzenia są wyświetlane na liście. Jeśli chcesz dodać produkt do kategorii, trzeba to zrobić na stronie Hierarchia kategorii zaopatrzenia lub na stronie Szczegóły pozycji.  
    * Domyślny typ aktualizacji określa, czy nowe produkty dodawane do hierarchii kategorii zaopatrzenia są natychmiast widoczne w katalogu. Jeśli jako typ aktualizacji ustawiono wartość Dynamiczne, zmiany są widoczne natychmiast. Jeśli typem aktualizacji jest Statyczne, nowe produkty są widoczne tylko dla osób używających katalogu po jego ponownym opublikowaniu. Akcja Publikuj jest dostępna w okienku akcji u góry strony. Jeśli produkty zostaną usunięte z hierarchii kategorii zaopatrzenia, zmiana jest natychmiast widoczna, niezależnie od wartości w polu Domyślny typ aktualizacji.  
8. Na liście znajdź i zaznacz odpowiedni rekord.
9. Kliknij przycisk Ukryj.
10. W okienku akcji kliknij pozycję Kategoria nawigacji.
11. Kliknij przycisk Wyłącz.
12. W okienku akcji kliknij pozycję Kategoria nawigacji.
13. Kliknij przycisk Włącz.
14. Kliknij opcję Uaktywnij katalog.
15. Zamknij stronę.

## <a name="make-the-catalog-visible"></a>Ustawianie widoczności katalogu
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zasady > Zasady zakupów.
2. Wybierz zasadę Procurement Policy USMF.
    * Należy wybrać zasady zakupów dla firmy, w której pracownik połączony z Twoim profilem użytkownika może zamawiać produkty. W danych firmy demonstracyjnej USMF administrator jest połączony z pracownikiem Julia Funderburk. Julia domyślnie zamawia produkty w USMF.  
3. Na liście kliknij łącze w wybranym wierszu.
4. Zaznacz nowo utworzony katalog.
5. Kliknij przycisk OK.
6. Zamknij stronę.
7. Zamknij stronę.

## <a name="use-the-catalog"></a>Używanie katalogu
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Wszystkie zapotrzebowania na zakup.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. Kliknij przycisk OK.
5. Kliknij przycisk Dodaj produkty.
6. Na liście znajdź i zaznacz odpowiedni rekord.
    * Do filtrowania produktów można używać hierarchii kategorii po lewej stronie lub filtru u góry listy.  
7. Kliknij opcję Dodaj do wierszy.
8. Na liście znajdź i zaznacz odpowiedni rekord.
9. Kliknij opcję Dodaj do wierszy.
10. Kliknij przycisk OK.


