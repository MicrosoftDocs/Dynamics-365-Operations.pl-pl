---
title: Tworzenie zwolnionego produktu dla jednej firmy
description: Ta procedura prowadzi przez proces tworzenia jednego zwolnionego produktu w ramach jednej jednostki prawnej.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 371157aee389694d349ec4fe51af0d9bfbf08cb7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213267"
---
# <a name="create-a-released-product-for-a-single-company"></a>Tworzenie zwolnionego produktu dla jednej firmy

[!include [banner](../../includes/banner.md)]

Ta procedura prowadzi przez proces tworzenia jednego zwolnionego produktu w ramach jednej jednostki prawnej. Po utworzeniu zwolnionego produktu jest on natychmiast dostępny tylko w tej jednostce. Instruktaż można wykonać przy użyciu danych firmy demonstracyjnej USMF. To zadanie jest zwykle wykonywane przez konstruktora produktów.


## <a name="create-a-released-product"></a>Tworzenie zwolnionego produktu
1. Przejdź do okna Zwolnione produkty.
2. Kliknij przycisk Nowy.
3. W polu Numer produktu wpisz wartość.
    * Jeśli w polu Numer produktu nie jest on automatycznie wprowadzony, wpisz unikatowy numer produktu. Ten krok jest wymagany tylko wtedy, jeśli żadna sekwencja numerów nie została skonfigurowana dla numerów produktów.  
4. W polu Nazwa produktu wpisz wartość.
    * Nazwa produktu jest ustawiona domyślnie jako alias. W razie potrzeby można zmienić alias.  
5. W polu Grupa modeli towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupy modeli produktu zawierają ustawienia określające sposób kontroli i obsługi towarów przy ich przyjmowaniu i wydawaniu. Ustawienia określają także sposób obliczania zużycia towarów.  
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Grupa towarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupy produktów służą do zarządzania zapasami przez dzielenie towarów magazynowych na grupy na podstawie ich charakterystyk. Na przykład, aby zarządzać sposobem księgowania informacji na kontach głównych, można utworzyć szereg różnych grup towarów skojarzonych z określonymi kontami głównymi. Dzięki temu można śledzić zmienną fizyczną wartość zapasów dla towarów w różnych etapach.  
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Na liście kliknij łącze w wybranym wierszu.
11. W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wymiary magazynowania umożliwiają sterowanie sposobem przechowywania towarów w magazynie i sposobem ich pobierania. Na przykład wymiar magazynowania może obejmować oddział i magazyn.  
12. Na liście znajdź i zaznacz odpowiedni rekord.
13. Na liście kliknij łącze w wybranym wierszu.
14. W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupa wymiarów śledzenia określa wymiary śledzenia, które można dodawać do produktu. Na przykład numer partii i numer seryjny mogą służyć do śledzenia pozycji magazynowych.  
15. Na liście znajdź i zaznacz odpowiedni rekord.
16. Na liście kliknij łącze w wybranym wierszu.
17. W polu Jednostka magazynowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Jednostka magazynowa określa sposób, w jaki produkt jest określany ilościowo podczas przechowywania w magazynie.  
18. Na liście znajdź i zaznacz odpowiedni rekord.
19. Na liście kliknij łącze w wybranym wierszu.
20. W polu Jednostka zakupu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Jednostka zakupu określa sposób, jaki produkt jest określany ilościowo podczas nabywana od dostawcy.  
21. Na liście znajdź i zaznacz odpowiedni rekord.
22. Na liście kliknij łącze w wybranym wierszu.
23. W polu Jednostka sprzedaży kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Jednostka sprzedaży określa sposób, w jaki produkt jest określany ilościowo podczas sprzedaży do odbiorcy.  
24. Na liście znajdź i zaznacz odpowiedni rekord.
25. Na liście kliknij łącze w wybranym wierszu.
26. W polu Jednostka BOM kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Jednostka listy składowej (BOM) określa sposób, w jaki produkt jest określany ilościowo podczas dołączania go do listy składowej (BOM).  
27. Na liście znajdź i zaznacz odpowiedni rekord.
28. Na liście kliknij łącze w wybranym wierszu.
29. W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupa podatków dla produktu w grupie opodatkowania sprzedaży określa sposób obliczania podatku dla każdego towaru.  
30. Na liście znajdź i zaznacz odpowiedni rekord.
31. Na liście kliknij łącze w wybranym wierszu.
32. W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupa podatków dla produktu w grupie opodatkowania zakupu określa sposób obliczania podatku dla każdego towaru.  
33. Na liście znajdź i zaznacz odpowiedni rekord.
34. Na liście kliknij łącze w wybranym wierszu.
35. Kliknij przycisk OK.

## <a name="add-product-characteristics"></a>Dodawanie cech produktu
1. Rozwiń lub zwiń sekcję Zarządzanie zapasami.
2. W polu Waga netto wpisz liczbę.
3. W polu Waga tara wpisz liczbę.
4. W polu Długość brutto wprowadź liczbę.
5. W polu Szerokość brutto wprowadź liczbę.
6. W polu Wysokość brutto wprowadź liczbę.
7. W polu Objętość wpisz liczbę.

## <a name="add-financial-dimensions"></a>Dodawanie wymiarów finansowych
1. Rozwiń lub zwiń sekcję Wymiary finansowe.
2. W polu BusinessUnit kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu CostCenter kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Dział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Na liście kliknij łącze w wybranym wierszu.
11. W polu ItemGroup kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
12. Na liście znajdź i zaznacz odpowiedni rekord.
13. Na liście kliknij łącze w wybranym wierszu.

