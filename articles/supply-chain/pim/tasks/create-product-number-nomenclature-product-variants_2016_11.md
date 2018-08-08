--- 
title: "Tworzenie numeru produktu dla skonfigurowanych wariantów produktu"
description: "Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym."
author: ShylaThompson
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e70a5f28635e75a69811085637f7e7431c0f1d40
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-product-number-for-configured-product-variants"></a>Tworzenie numeru produktu dla skonfigurowanych wariantów produktu

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym. W procedurze zademonstrowano również, jak zbudować konwencję nazewnictwa konfiguracji dla składnika modelu konfiguracji produktu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Nowa konwencja nazewnictwa numerów produktu jest przypisana do produktu głównego D0004. Zazwyczaj zadanie wykonuje projektant produktów.


## <a name="create-a-product-number-nomenclature"></a>Tworzenie konwencji nazewnictwa numerów produktu
1. Kliknij opcję Definicja modelu wariantu produktu.
2. Kliknij opcję Nazewnictwo produktów.
3. Kliknij przycisk Nowy.
4. W polu Nazwa wpisz wartość.
5. Wypełnij pole Opis.
6. Kliknij przycisk Dodaj.
7. Kliknij opcję Numer produktu głównego.
8. Kliknij przycisk Dodaj.
9. Kliknij opcję Stała tekstowa.
10. Na liście oznacz wybrany wiersz.
11. W polu Tekst wpisz wartość.
12. Kliknij przycisk Dodaj.
13. Kliknij opcję Konfiguracja.
14. Zamknij stronę.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Przypisywanie konwencji nazewnictwa numerów produktu do produktu głównego
1. Kliknij opcję Produkty główne.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Numer produktu z wartością „D”.
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij przycisk Edytuj.
5. W polu Użyj nazewnictwa zaznacz opcję Tak.
6. W polu Nazewnictwo numerów wariantów produktu wprowadź lub wybierz wartość.
7. Zamknij stronę.
8. Zamknij stronę.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Tworzenie konwencji nazewnictwa dla składnika modelu konfiguracji produktu
1. Kliknij opcję Modele konfiguracji produktu.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij przycisk Edytuj.
5. W polu Użyj nazewnictwa konfiguracji zaznacz opcję Tak.
6. Kliknij przycisk Dodaj.
7. Kliknij opcję Wartość atrybutu.
8. Na liście oznacz wybrany wiersz.
9. Wprowadź lub wybierz wartość w polu Atrybut.
10. Kliknij przycisk Dodaj.
11. Kliknij opcję Stała tekstowa.
12. Na liście oznacz wybrany wiersz.
13. W polu Tekst wpisz wartość.
14. Kliknij przycisk Dodaj.
15. Kliknij opcję Wartość atrybutu.
16. Na liście oznacz wybrany wiersz.
17. Wprowadź lub wybierz wartość w polu Atrybut.
18. Kliknij przycisk Dodaj.
19. Kliknij opcję Stała tekstowa.
20. Na liście oznacz wybrany wiersz.
21. W polu Tekst wpisz wartość.
22. Kliknij przycisk Dodaj.
23. Kliknij opcję Wartość atrybutu.
24. Na liście oznacz wybrany wiersz.
25. Wprowadź lub wybierz wartość w polu Atrybut.
26. Kliknij przycisk Dodaj.
27. Kliknij opcję Stała tekstowa.
28. Na liście oznacz wybrany wiersz.
29. W polu Tekst wpisz wartość.
30. Kliknij przycisk Dodaj.
31. Kliknij opcję Wartość atrybutu.
32. Na liście oznacz wybrany wiersz.
33. Wprowadź lub wybierz wartość w polu Atrybut.
34. Kliknij przycisk Dodaj.
35. Kliknij opcję Stała tekstowa.
36. Na liście oznacz wybrany wiersz.
37. W polu Tekst wpisz wartość.
38. Kliknij przycisk Dodaj.
39. Kliknij opcję Wartość sekwencji numerów.
40. Na liście oznacz wybrany wiersz.
41. W polu Sekwencja numerów wprowadź lub wybierz wartość.
42. Zamknij stronę.
43. Zamknij stronę.
44. Zamknij stronę.


