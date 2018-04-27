--- 
title: "Tworzenie kolejności ponagleń"
description: "Ten przewodnik po zadaniach umożliwia tworzenie kolejki ponagleń."
author: mikefalkner
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6331c3680169b305c4bfbfada4ba106b619be092
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-collection-letter-sequence"></a>Tworzenie kolejności ponagleń

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ten przewodnik po zadaniach umożliwia tworzenie kolejki ponagleń. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Kredyty i windykacja > Ustawienia > Konfiguruj kolejność ponagleń.
2. Kliknij przycisk Nowy.
3. W polu Kolejność ponagleń wpisz identyfikator kolejności, który będzie reprezentował kolejność. Będzie on używany podczas konfigurowania profilu księgowania.
4. Wypełnij pole Opis.
    * Warunki płatności są opcjonalne. Jeśli wprowadzisz wartość w tym polu, faktura za opłaty z ponaglenia będzie używała tych warunków płatności zamiast warunków płatności zapisanych dla odbiorcy.  
5. W polu Kod ponaglenia wybierz kod pierwszego ponaglenia, które ma zostać wysłane.
    * Pierwsze ponaglenie jest tworzone na podstawie terminu zapłaty na fakturze, wartości okresu prolongaty wprowadzonej w polu Dni w tym wierszu oraz innych informacji wprowadzonych w tym wierszu.  
6. Wypełnij pole Opis.
    * Domyślnie walutą opłaty będzie waluta odbiorcy. Ten kod waluty może się różnić od kodu waluty faktury.  
7. Kliknij przycisk Dodaj, aby dodać następne ponaglenie w kolejności, które zostanie wysłane.
    * W wielu przypadkach pierwsze ponaglenie jest tylko ostrzeżeniem. W razie potrzeby można dodać opłaty.  
8. W polu Kod ponaglenia wybierz kod następnego w kolei ponaglenia, które ma zostać wysłane.
9. W polu Opis wpisz wartość.
10. W polu konta głównego wybierz konto przychodów, które będzie używane dla opłat.
11. Wprowadź opłatę, która będzie naliczana podczas księgowania tego ponaglenia.
12. W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Zaznacz grupę podatków dla towaru, jeśli należy obliczyć podatki od opłaty.  
13. Na liście kliknij łącze w wybranym wierszu.
14. Wprowadź minimalne saldo zaległości, jakie jest wymagane, zanim zostanie wysłane ponaglenie.
15. Wprowadź liczbę dni prolongaty, na jaką chcesz pozwolić.
    * Jest to liczba dni po terminie płatności, kiedy można wygenerować ponaglenie. Termin płatności używany do obliczania zależy od miejsca ponaglenia w kolejce ponagleń:   ⦁    Okres prolongaty ponaglenia 1 jest względny wobec terminu płatności na fakturze.  ⦁ Okres prolongaty ponaglenia 2 i kolejnych jest względny wobec daty zaksięgowania lub wydrukowania poprzedniego ponaglenia, zależnie od opcji wybranej w polu Aktualizacja kodu ponaglenia na stronie Parametry modułu rozrachunków z odbiorcami.  
16. Kliknij przycisk Dodaj, aby dodać ostatnie ponaglenie w kolejności.
    * W kolejce ponagleń można dodać maksymalnie pięć kodów ponagleń.  
17. W polu Kod ponaglenia wybierz kod następnego w kolei ponaglenia, które ma zostać wysłane.
18. W polu Opis wpisz wartość.
19. W polu Konto główne podaj żądane wartości.
20. W polu Opłata w walucie wpisz liczbę.
21. W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
22. Na liście kliknij łącze w wybranym wierszu.
23. W polu Minimalne saldo zaległości wpisz liczbę.
24. W polu Dni wpisz liczbę.
25. To pole wyboru należy zaznaczyć, aby zablokować możliwość tworzenia kolejnych dostaw i faktur dla danego odbiorcy.
    * Aby odblokować konto, wybierz Nie w Fakturowanie i dostawy zablokowane na stronie Klientów.  
26. Rozwiń skróconą kartę Notatka.
27. Wprowadź tekst, jaki ma być wyświetlany dla ponaglenia o wybranym kodzie.
    * Ten tekst można przetłumaczyć na wiele języków za pomocą menu Tłumaczenia widocznego nad polem notatki.  


