---
title: Tworzenie kolejności ponagleń
description: Ta procedura służy do tworzenie kolejności ponagleń.
author: JodiChristiansen
ms.date: 12/07/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af5d0a001fbe705834e116516933be67f2de8826
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734167"
---
# <a name="create-a-collection-letter-sequence"></a>Tworzenie kolejności ponagleń

[!include [banner](../../includes/banner.md)]

Ta procedura służy do tworzenie kolejności ponagleń. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje **Kredyty i windykacja > Ustawienia > Konfiguruj kolejność ponagleń**.
2. Kliknij przycisk **Nowy**.
3. W polu **Kolejność ponagleń** wpisz identyfikator kolejności, który będzie reprezentował kolejność. Będzie on używany podczas konfigurowania profilu księgowania.
4. W polu **Opis** wpisz wartość. Warunki płatności są opcjonalne. Jeśli wprowadzisz wartość w tym polu, faktura za opłaty z ponaglenia będzie używała tych warunków płatności zamiast warunków płatności zapisanych dla odbiorcy.  
5. W polu **Kod ponaglenia** wybierz kod pierwszego ponaglenia, które ma zostać wysłane. Pierwsze ponaglenie jest tworzone na podstawie terminu zapłaty na fakturze, wartości okresu prolongaty wprowadzonej w polu Dni w tym wierszu oraz innych informacji wprowadzonych w tym wierszu.  
6. W polu **Opis** wpisz wartość. 
7. Waluta domyślna opłaty to waluta osoby prawnej. Ten kod waluty może się różnić od kodu waluty faktury.   
8. Kliknij przycisk **Dodaj**, aby dodać następne ponaglenie w kolejności, które zostanie wysłane. W wielu przypadkach pierwsze ponaglenie jest tylko ostrzeżeniem. W razie potrzeby można dodać opłaty.  
9. W polu **Kod ponaglenia** wybierz kod następnego w kolei ponaglenia, które ma zostać wysłane.
10. W polu **Konto główne** wybierz konto przychodów, które będzie używane dla opłat.
11. Wprowadź opłatę, która będzie naliczana podczas księgowania tego ponaglenia.
12. W polu **Grupa podatków dla towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie. Zaznacz grupę podatków dla towaru, jeśli należy obliczyć podatki od opłaty.  
13. Na liście kliknij łącze w wybranym wierszu.
14. W polu **Minimalne saldo zaległości** wprowadź Minimalne saldo zaległości wymagane przed wysłaniem ponaglenia.
15. W polu **Dni** wprowadź liczbę dni prolongaty, na jaką chcesz pozwolić. Jest to liczba dni po terminie płatności, kiedy można wygenerować ponaglenie. Termin płatności używany do obliczania zależy od miejsca ponaglenia w kolejce ponagleń:
    - Okres prolongaty ponaglenia 1 jest względny wobec terminu płatności na fakturze.
    - Okres prolongaty ponaglenia 2 i kolejnych jest względny wobec daty zaksięgowania lub wydrukowania poprzedniego ponaglenia, zależnie od opcji wybranej w polu Aktualizacja kodu ponaglenia na stronie Parametry modułu rozrachunków z odbiorcami.  
16. Kliknij przycisk **Dodaj**, aby dodać ostatnie ponaglenie w kolejności. W kolejce ponagleń można dodać maksymalnie pięć kodów ponagleń.  
17. W polu **Kod ponaglenia** wybierz kod następnego w kolei ponaglenia, które ma zostać wysłane.
18. W polu **Opis** wpisz wartość.
19. W polu **Konto główne** podaj żądane wartości.
20. W polu **Opłata w walucie** wpisz liczbę.
21. W polu **Grupa podatków dla towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
22. Na liście kliknij łącze w wybranym wierszu.
23. W polu **Minimalne saldo zaległości** wpisz liczbę.
24. W polu **Dni** wpisz liczbę.
25. Zaznacz pole wyboru **Blokuj**, aby zablokować możliwość tworzenia kolejnych dostaw i faktur dla danego odbiorcy. Aby odblokować konto, wybierz **Nie** w **Fakturowanie i dostawy zablokowane** na stronie **Klientów**.  
26. Rozwiń skróconą kartę **Notatka**.
27. Wprowadź tekst, jaki ma być wyświetlany dla ponaglenia o wybranym kodzie. Ten tekst można przetłumaczyć na wiele języków za pomocą menu **Tłumaczenia** widocznego nad polem notatki.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
