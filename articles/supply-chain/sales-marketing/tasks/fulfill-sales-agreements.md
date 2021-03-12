---
title: Realizacja umów sprzedaży
description: W tej procedurze pokazano, jak zrealizować zamówienie sprzedaży poprzez skojarzenie z nim umowy sprzedaży.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines, SalesAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fca2f8777f5ce3b6a96be7fcab4f011aefd9d80b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991771"
---
# <a name="fulfill-sales-agreements"></a>Realizacja umów sprzedaży

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak zrealizować zamówienie sprzedaży poprzez skojarzenie z nim umowy sprzedaży. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Przed rozpoczęciem tego przewodnika upewnij się, że masz obowiązującą umowę sprzedaży typu „Zobowiązanie co do wartości produktu”. Można także uruchomić przewodnik po zadaniach o nazwie „Tworzenie umów sprzedaży”.  




## <a name="release-a-sales-order-from-the-agreement"></a>Zwalnianie zamówienia sprzedaży z poziomu umowy
1. Wybierz kolejno opcje Sprzedaż i marketing > Umowy sprzedaży > Umowy sprzedaży.
2. Na liście otwórz umowę, dla której chcesz zwolnić zamówienie.
3. W okienku akcji kliknij opcję Umowa sprzedaży.
4. Kliknij opcję Zwolnij zamówienie.
    * Jak wskazuje tekst u góry strony Tworzenie zlecenia wydania, szczegóły wymagane w wierszach zamówienia sprzedaży będą się różnić w zależności od tego, czy umowa jest oparta na ilości czy wartości.  
    * Umowy w tym przewodniku jest typu „Zobowiązanie co do wartości produktu”. To dlatego na tej stronie sekcja Wiersze jest pusta. Gdyby zobowiązanie było oparte na ilości, informacje w wierszach zostałyby skopiowane z umowy.  
5. Kliknij przycisk Utwórz.
    * Komunikat informuje, że zamówienia sprzedaży zostało utworzone. Ponieważ zamówienie nie zawiera żadnych wierszy, w celu ukończenia procesu zwalniania należy dodać szczegóły wierszy zamówienia.   
6. Zamknij stronę.
7. Zamknij stronę.
8. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.
9. Na liście znajdź i otwórz zamówienie, które zostało utworzone w wyniku zwolnienia zamówienia w poprzednim zadaniu.
10. Kliknij przycisk Dodaj wiersz.
11. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
12. W polu Numer towaru wpisz lub wybierz towar, który znajduje się w skojarzonej umowie sprzedaży.
13. Wprowadź liczbę w polu Ilość.
    * Upewnij się, że wprowadzisz taką ilość, że pole Kwota netto będzie zawierało wartość niższą niż w skojarzonej umowie sprzedaży.  
    * Należy zauważyć, że ponieważ zamówienie sprzedaży jest połączone z umową, wynegocjowany procent rabatu jest stosowany do wiersza zamówienia.  
14. Kliknij opcję Aktualizuj wiersz.
15. Kliknij opcję Powiązany.
    * Strona Dołączona umowa zawiera identyfikator i warunki umowy, z której wiersz jest zwalniany.  
16. Zamknij stronę.
17. W okienku akcji kliknij pozycję Ogólne.
18. Kliknij opcję Dołączona umowa sprzedaży.
19. Rozwiń sekcję Szczegóły wiersza.
20. Kliknij kartę Realizacja.
    * Karta Realizacja zawiera podsumowanie wszystkich wierszy zamówienia sprzedaży, które są skojarzone z tym zobowiązaniem, oraz ich stany realizacji, a także kwotę lub ilość, która nie została jeszcze zwolniona.   
21. Zamknij stronę.
22. Zamknij stronę.
23. Zamknij stronę.

## <a name="apply-sales-agreement-in-the-order-process"></a>Stosowanie umowy sprzedaży w procesie zamawiania
1. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i wybierz odbiorcę podanego w umowie sprzedaży.
5. Na liście kliknij łącze w wybranym wierszu.
6. Rozwiń sekcję Ogólne.
7. W polu Identyfikator umowy sprzedaży kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście kliknij łącze w wybranym wierszu.
9. Kliknij przycisk Tak.
10. Kliknij przycisk OK.
11. Na liście oznacz wybrany wiersz.
12. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
13. W polu Numer towaru wpisz lub wybierz towar, który znajduje się w skojarzonej umowie sprzedaży.
14. Na liście kliknij łącze w wybranym wierszu.
15. Kliknij przycisk Zapisz.
16. W okienku akcji kliknij opcję Pobierz i zapakuj.
17. Kliknij opcję Księguj dokument dostawy.
18. Rozwiń sekcję Parametry.
19. W polu Księgowanie wybierz opcję Tak.
20. Kliknij przycisk OK.
21. Kliknij przycisk OK.
22. W okienku akcji kliknij pozycję Ogólne.
23. Kliknij opcję Dołączona umowa sprzedaży.
24. Kliknij kartę Realizacja.

