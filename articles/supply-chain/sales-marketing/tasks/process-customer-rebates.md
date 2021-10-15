---
title: Generowanie i przetwarzanie rabatów dla odbiorców
description: Ta procedura przedstawia sposób przetwarzania rabatów dla odbiorców na etapach od wygenerowania wniosku do przekazania ich jako naliczenia do modułu Rozrachunki z odbiorcami.
author: Henrikan
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PdsRebateAgreement, SalesTableListPage, SalesCreateOrder, SalesTable, MCRPriceHistory, SalesEditLines,  PdsRebateTableListPage, MCRBrokerWriteOffReason, MRCHierarchyAddCust, PdsItemRebateGroup, PdsRebate, PdsRebateProgramTMATable, PdsRebateTable, PdsRebateTableListPagePreviewPane, PdsRebateTrans, PdsRebateType_CustLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 355ca6b8a06b15b68e0fd6236999b4e64a83bf2a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573352"
---
# <a name="generate-and-process-customer-rebates"></a>Generowanie i przetwarzanie rabatów dla odbiorców

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia sposób przetwarzania rabatów dla odbiorców na etapach od wygenerowania wniosku do przekazania ich jako naliczenia do modułu Rozrachunki z odbiorcami. Prowadzi przez kolejne fazy konkretnego przykładu w celu wyjaśnienia wpływu różnych warunków w wierszach rabatu na końcowe kwoty, które zostaną uznane dla odbiorcy. Przed rozpoczęciem zadań z przewodnika należy użyć danych firmy demonstracyjnej USMF i wykonać następujące zadania: (1) Przejdź do strony Parametry modułu rozrachunków z odbiorcami, rozwiń kartę Ceny, rozwiń kartę Szczegóły ceny i upewnij się, że opcja Włączanie szczegółów ceny ma ustawioną wartość Tak. (2) Przejdź do strony Umowy rabatowe i zaznacz umowę rabatową z odbiorcą USMF-000001. Jeśli pole Stan zatwierdzania w ramach przepływu pracy nie ma ustawionej wartości Zatwierdzone, w okienku akcji kliknij opcję Weryfikacja, aby zatwierdzić umowę.


## <a name="review-a-customer-rebate-agreement"></a>Przeglądanie umowy rabatowej z odbiorcą
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Sprzedaż i marketing > Rabaty dla odbiorców > Umowy rabatowe**.
    - Następnych kilka kroków dotyczy warunków umowy USMF 000001. Dzięki temu łatwiej zrozumieć sposób obliczania wartości kredytu odbiorcy w dalszej części procedury.  
    - Umowa jest dla jednego odbiorcy, w tym przykładzie odbiorcy US-009.  
    - Rabaty są oferowane odbiorcy podczas kupowania określonego produktu. W tym przypadku produkt ma numer T0020.   
    - Zakupy odbiorcy, od których szacuje się kwoty rabatu, będą sumowane w cyklu tygodniowym.  
    - Ustawienie „Cena pobierana z” zawiera wartość Brutto, co oznacza, że kwota sprzedaży w wierszu, na podstawie której szacuje się wartość wniosku, nie jest pomniejszana przez rabat wiersza.  
    - Pole Typ podziału wiersza rabatu przedstawia metodę obliczania rabatów. W tym przypadku cel sprzedaży, względem którego mają być szacowane rabaty, to Ilość.   
    - Wiersze umowy określają typ kwoty rabatu, rzeczywistą wartość rabatu i wartości progowe. W tym przykładzie odbiorca będzie się kwalifikował na rabat w wysokości 20 USD za każdą kupioną sztukę, jeśli tygodniowy zakup produktów mieści się w zakresie od 1 do 50 sztuk, a na rabat w wysokości 40 USD za sztukę w przypadku nabycia powyżej 50 sztuk.  
2. Zamknij stronę.

## <a name="generate-rebate-claims"></a>Generowanie wniosków rabatowych
1. Przejdź do **Okienko nawigacyji > Moduły > Sprzedaż i marketing >Wszystkie zamówienia sprzedaży**.
2. Kliknij przycisk **Nowy**. Aby zilustrować sposób generowania wniosków rabatowych, następne zadanie polega na utworzeniu zamówienia sprzedaży, w którym produkt i ilość będą kwalifikowały odbiorcę na rabat.    
3. W polu **Konto odbiorcy** wprowadź lub wybierz wartość.
4. Kliknij przycisk **OK**.
5. W polu **Kod towaru** wpisz lub wprowadź wartość.
6. W polu **Ilość** wpisz wartość 40.
7. W sekcji **Linie zamówienia sprzedaży** wybierz opcję **Linia zamówienia sprzedaży**.
8. Kliknij opcję **Szczegóły ceny**. Jeśli ta opcja nie jest widoczna, to dlatego, że przed uruchomieniem przewodnika nie ustawiono wartości „Tak” w opcji **Włączanie szczegółów ceny**.     
9. Rozwiń sekcję **Rabaty**. Na karcie **Rabaty** znajduje się lista wszystkich umów rabatowych, które mają zastosowanie do bieżącego wiersza zamówienia, oraz jest wyświetlana szacowana kwota rabatu. Zwróć uwagę, że wyświetlane kwoty są tylko orientacyjnymi wskazaniami, na ile mogą opiewać przyszłe wnioski rabatowe. Rzeczywiste kwoty rabatów mogą być inne w zależności od następujących czynników: łączna wielkość zakupów dokonanych przez odbiorcę w ramach okresowej umowy rabatowej; czy odbiorca zwrócił wszystkie ilości czy tylko część; czy odnośne zamówienie sprzedaży zostało zafakturowane.
10. Zamknij stronę.
11. Kliknij przycisk **Dodaj wiersz.**
12. W polu **Kod towaru** wpisz lub wprowadź wartość.
13. W polu **Ilość** wpisz wartość 60.
14. Kliknij przycisk **Zapisz**.
15. W **okienku akcji** kliknij pozycję **Faktura**.
16. Kliknij opcję **Faktura**.
17. Rozwiń sekcję **Parametry**.
18. W polu **Ilość** zaznacz opcję „Wszystko”.
19. Kliknij przycisk **OK**.
20. Kliknij przycisk **OK**.

## <a name="process-rebate-claims"></a>Przetwarzanie roszczeń dotyczących rabatu
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Sprzedaż i marketing > Rabaty dla odbiorców > Rabaty**.
    - Strona rabaty pełni rolę pulpitu, na którym można przeglądać, zatwierdzać i przetwarzać wnioski rabatowe. Teraz będziesz przetwarzać wnioski, które zostały utworzone w wyniku zafakturowania zamówienia sprzedaży dla odbiorcy US-009 będącego stroną umowy rabatowej USMF-000001.   
    - Pierwszy wiersz reprezentuje wniosek rabatowy na 800 USD wynikający ze sprzedaży 40 sztuk produktu T0020 z rabatem 20 USD za sztukę. Jest to zgodne z warunkami pierwszego przedziału ilości w umowie rabatowej.  
    - Drugi wniosek jest na 2400 USD i wynika ze sprzedaży 60 sztuk produktu T0020 z rabatem 40 USD za sztukę, zgodnie z drugim przedziałem ilości w umowie.  
    - Oba wnioski znajdują się w stanie „Do obliczenia”. Oznacza to, że są one skojarzone z umową, która śledzi wyniki zakupowe odbiorcy w regularnych odstępach czasu, i muszą być ponownie obliczane w celu uwzględnienia łącznej wielkości sprzedaży w odnośnym okresie.   
2. Kliknij opcję **Kumuluj**.
3. W polu **Odbiorca** wprowadź lub wybierz wartość.
4. W polu **Data początkowa** wybierz dzisiejszą datę.
5. Kliknij przycisk **OK**. W wyniku uruchomienia funkcji **kumulacji** szacowana kwota wniosku została teraz skorygowana, aby uwzględnić fakt, że całkowita wielkości sprzedaży dla odbiorcy w okresie jest wyższa niż podczas generowania pierwszego rabatu. Dokładniej rzecz biorąc: ponieważ łączna ilość zakupu osiągnęła 100 sztuk, odbiorca kwalifikuje się na rabat 40 USD za sztukę (zgodnie z drugim przedziałem ilości w umowie), czyli łącznie 400 USD kwoty rabatu. Różnica została zarejestrowana jako nowa „korekta” wniosku na dodatkowe 800 USD. Stan wniosków rabatowych uwzględnionych w aktualizacji kumulacji jest teraz ustawiony na Obliczone. 
6. Na liście zaznacz wszystkie wiersze.
7. Kliknij przycisk **Zatwierdź**.
8. Kliknij przycisk **Przetwarzaj**.
9. W polu **Odbiorca** wprowadź lub wybierz wartość.
10. Kliknij przycisk **OK**. Komunikat pokazuje, że rabat został pomyślnie przetworzony, a stan wniosków zmienił się na Zaznacz. Oznacza to, że w wyniku księgowania arkusza naliczania rabatu:
    - Roszczenia teraz zostały przeniesione do tymczasowego salda odbiorcy jako potrącenia.
    - Konto naliczania rabatów zostało uznane kwotą reprezentującą przyszłe zobowiązanie odbiorcy.
    - Konto wydatków rabatowych zostało obciążone kwotą reprezentującą koszt poniesiony w związku ze sprzedażą.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
