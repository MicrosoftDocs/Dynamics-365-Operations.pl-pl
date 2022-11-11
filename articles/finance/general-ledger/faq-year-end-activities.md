---
title: Działania na koniec roku — często zadawane pytania
description: W tym artykule można znaleźć pytania, które mogą powstać podczas zamknięcia roku, oraz odpowiedzi, które mogą pomóc w działaniach związanych z zamknięciem roku.
author: moaamer
ms.date: 11/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a75d1e3e68837a437b2369ba369b0063e015b12
ms.sourcegitcommit: 78cbb125f20a33df38bda0546203b8f837cbcd93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2022
ms.locfileid: "9751966"
---
# <a name="year-end-activities-faq"></a>Działania na koniec roku — często zadawane pytania 

[!include [banner](../includes/banner.md)]

W tym artykule można znaleźć pytania, które mogą powstać podczas zamknięcia roku, oraz odpowiedzi, które mogą pomóc w działaniach związanych z zamknięciem roku. Informacje zawarte w tym artykule skupiają się głównie wokół pytań dotyczących działań związanych z zamknięciem roku w obszarach Księga główna i Rozrachunki z dostawcami.

## <a name="general-ledger-year-end-enhancements"></a>Ulepszenia na koniec roku w księdze głównej 
W wersji 10.0.20 wprowadzono ulepszenie zamknięcia na koniec roku, które jest domyślnie włączone począwszy od wersji 10.0.25. Jeśli w organizacji jest używana wersja wcześniejsza niż 10.0.25, zaleca się włączenie tej funkcji przed rozpoczęciem procesu zamknięcia na koniec roku. Aby używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego Zarządzanie funkcjami, aby sprawdzić stan funkcji i ją włączyć, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

 - Moduł: Księga główna
 - Nazwa funkcji: Ulepszenia na koniec roku w księdze głównej

Konfiguracja szablonów zamknięcia roku została przeniesiona na nową stronę ustawień, **Konfiguracja szablonu zamknięcia roku**. Istniejąca strona zamknięcia na koniec roku zmieni się w sposób podobny do przeszacowania w walucie obcej w księdze głównej, gdzie lista będzie wyświetlana za każdym razem, gdy zamknięcie na koniec roku zostanie uruchomione lub wycofane. Kierownik ds. księgowości może inicjować zamknięcie na koniec roku z nowej strony. 

Aby wycofać zamknięcie na koniec roku, wybierz ostatni rok obrachunkowy dla odpowiedniej osoby prawnej i wybierz przycisk **Wycofaj zamknięcie na koniec roku**. Wycofanie spowoduje usunięcie wpisów księgowych dla poprzedniego zamknięcia na koniec roku i nie spowoduje automatycznego ponownego uruchomienia zamknięcia na koniec roku. 

Zamknięcie na koniec roku można uruchomić ponownie, uruchamiając proces po raz kolejny dla roku obrachunkowego i osoby prawnej. Proces będzie nadal korzystać z ustawienia parametru Księga główna, aby ustalić, czy ponowne zamknięcie na koniec roku będzie rozliczać tylko nowe lub zmienione transakcje, czy też całkowicie wycofa poprzednie zamknięcie i ponownie uruchomi proces dla wszystkich transakcji.  

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Księga główna: skąd wiadomo, że proces zamknięcia na koniec roku jest uruchamiany, a nie wycofywany?
Wielokrotnie spotykaliśmy się z sytuacją, gdy organizacja próbuje uruchomić zamknięcie na koniec roku, zamiast tego dokonuje jednak cofnięcia zamknięcia na koniec roku. Jeśli zamknięcie na koniec roku nastąpi bardzo szybko albo nie spowoduje wygenerowania sald otwarcia, sprawdź ustawienie **Cofnij poprzednie zamknięcie** w obszarze **Zamknięcie na koniec roku** (**Księga główna > Zamknięcie okresu > Zamknięcie na koniec roku > Uruchom zamknięcie obrachunkowe**). 

[![Uruchamianie i cofanie procesu zamknięcia na koniec roku.](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Jeśli dla funkcji **Cofnij poprzednie zamknięcie** wybrano opcję **Tak**, poprzednie zamknięcie na koniec roku zostanie cofnięte. W przypadku uruchomienia operacji cofnięcia wszystkie wpisy salda zamknięcia i salda otwarcia zostaną usunięte, tak jakby zamknięcie na koniec roku nigdy nie zostało uruchomione. Załączniki zostaną usunięte. Zamknięcie na koniec roku nie zostanie ponownie uruchomione automatycznie. Konieczne będzie ponowne rozpoczęcie procesu, przy czym tym razem należy dla opcji **Cofnij poprzednie zamknięcie** wybrać ustawienie **Nie**. 

> [!NOTE]
> Wpis salda zamknięcia jest opcjonalnie tworzony w zamykanym roku. Dzieje się tak tylko wtedy, gdy parametr księgi głównej **Tworzenie transakcji zamknięcia podczas transferu** ma wartość **Tak**. Wpis salda otwarcia jest tworzony zawsze, ponieważ jest to saldo początkowe dla następnego roku.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Księga główna: jaka jest różnica między parametrami księgi głównej Cofnij i Usuń dla zamknięcia na koniec roku?
Istnieją dwie pozycje, które ze względu na pewne podobieństwo mogą się mylić. Warto zwrócić uwagę na różnice między nimi. **Cofnij poprzednie zamknięcie** to funkcja dostępna z poziomu okna dialogowego **Zamknięcie na koniec roku**, natomiast **Usuwanie transakcji zamknięcia roku podczas przenoszenia** to parametr księgi głównej (**Księga główna > Zamknięcie okresu > Zamknięcie na koniec roku > Uruchom zamknięcie obrachunkowe**).  

[![Różnica między funkcją Cofnij a parametrem księgi głównej Usuń dla zamknięcia na koniec roku.](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Wybierz polecenie **Cofnij poprzednie zamknięcie** w rozwijanym menu dialogowym podczas uruchamiania procesu zamknięcia na koniec roku, aby usunąć wszystkie wpisy salda zamknięcia i salda otwarcia, tak jakby zamknięcie na koniec roku nigdy nie zostało uruchomione. Załączniki zostaną usunięte. Zamknięcie na koniec roku nie zostanie ponownie uruchomione automatycznie. Aby uruchomić zamknięcie na koniec roku, należy ponownie zainicjować ten proces, tym razem zmieniając ustawienie funkcji **Cofnij poprzednie zamknięcie** na **Nie** (**Księga główna > Ustawienia księgi > Parametry księgi głównej**). 

[![Ustawienie parametru księgi głównej.](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

Parametr **Usuwanie transakcji zamknięcia roku podczas przenoszenia** w księdze głównej jest używana tylko w przypadku uruchamiania (a nie wycofywania) zamknięcia na koniec roku (opcja **Cofnij poprzednie zamknięcie** ma ustawienie **Nie**). Jeśli ten parametr ma wartość **Tak**, wszystkie wpisy salda zamknięcia i salda otwarcia zostaną usunięte, a zamknięcie na koniec roku zostanie ponownie uruchomione. Ten proces stosuje się, gdy organizacja chce, aby wszystkie transakcje, w tym korekty od ostatniego zamknięcia na koniec roku, zastały zaksięgowane w jednym wpisie księgowania dla wpisów salda zamknięcia i salda otwarcia. 

Jeśli ta opcja ma wartość **Nie**, wszystkie wpisy salda zamknięcia i salda otwarcia zostaną pozostawione. Nie zostaną one usunięte. Zamiast tego zostanie utworzony nowy wpis salda zamknięcia i salda otwarcia jedynie dla różnicy albo dla nowych transakcji zaksięgowanych od ostatniego zamknięcia na koniec roku mającego miejsce w danym roku obrachunkowym.  

> [!NOTE]
> Wpis salda zamknięcia jest tworzony w zamykanym roku. Dzieje się tak tylko wtedy, gdy parametr **Tworzenie transakcji zamknięcia podczas transferu** w księdze głównej ma wartość **Tak**. Wpis salda otwarcia jest tworzony zawsze, ponieważ jest to saldo początkowe dla następnego roku. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Księga główna: co można zmienić, aby zwiększyć wydajność przetwarzania na koniec roku? 
W celu poprawy wydajności zamknięcia na koniec roku można wprowadzić wiele zmian. Zalecamy rozważenie sugerowanych zmian w celu podjęcia decyzji w kwestii tego, czy są one odpowiednie dla organizacji.  

### <a name="dimension-sets"></a>Zestawy wymiarów
Podczas uruchamiania procesu zamknięcia na koniec roku następuje przebudowa sald poszczególnych zestawów wymiarów, co ma bezpośredni wpływ na wydajność. Niektóre organizacje tworzą zestawy wymiarów niepotrzebnie, tylko dlatego, że były one używane w przeszłości lub mogły zostać kiedyś użyte.  Te niepotrzebne zestawy wymiarów są dalej przebudowywane podczas realizacji procesu zamknięcia na koniec roku, co wydłuża czas jego trwania. Poświęć nieco czasu na ocenę zestawów wymiarów i usunięcie tych z nich, które nie są potrzebne.

Zbędne zestawy wymiarów wpływają również na przebieg zadania wsadowego **BudgetDimensionFocusInitializeBalance** (**Księga główna > Plan kont > Wymiary > Zestawy wymiarów finansowych**).

[![Zestawy wymiarów finansowych.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Konfiguracja szablonu zamknięcia na koniec roku
Szablon zamknięcia na koniec roku pozwala organizacjom wybrać poziom wymiaru finansowego do obsługi podczas przenoszenia sald kont wynikowych do wstrzymanych dochodów. Ustawienia umożliwiają organizacji obsługę szczegółowych wymiarów finansowych (**Zamknij wszystko**) podczas przenoszenia sald do wstrzymanych dochodów lub podjęcie decyzji o podsumowaniu kwot w ramach wartości jednego wymiaru (**Zamknij jeden**). Możliwe jest jego zdefiniowanie dla każdego wymiaru finansowego. Aby uzyskać więcej informacji dotyczących tych ustawień, zobacz artykuł [Zamknięcie na koniec roku](year-end-close.md).

Zalecamy ocenę wymagań organizacji i, jeśli to możliwe, zamknięcie możliwie wielu wymiarów za pomocą opcji **Zamknij jeden** dotyczącej końca roku, aby poprawić wydajność. Po zamknięciu wartości (która może być także wartością pustą) jednego wymiaru system określa mniej szczegółów podczas ustalania sald dla zapisów na koncie wstrzymanych dochodów.

## <a name="degenerate-dimensions"></a>Zdegeneruj wymiary

Wymiar zdegenerowany zapewnia brak możliwości ponownego użycia jest samego i w połączeniu z innymi wymiarami. Istnieją dwa typy wymiarów zdegenerowanych. Pierwszy typ to wymiar, który jest indywidualnie degenerowany. Zazwyczaj ten typ wymiaru degenerowanego pojawia się tylko w jednej transakcji lub w małych zestawach transakcji. Drugi typ jest wymiarem, który staje się degenerowany w połączeniu z jednym lub większą liczbą dodatkowych wymiarów wykazujących te same możliwości na podstawie dostępnych permutacji, które można generować. Wymiar zdegenerowany może mieć znaczący wpływ na wydajność procesu zamknięcia na koniec roku. Aby zminimalizować problemy z wydajnością, w konfiguracji zamknięcia na koniec roku zdefiniuj wszystkie wymiary zdegenerowane jako **Zamknij jeden**, tak jak opisano w poprzedniej sekcji.

## <a name="general-ledger-what-does-the-period-close-year-end-close-do"></a>Księga główna: Czym jest zamknięcie okresu, zamknięcie na koniec roku?
 
[![Zamknięcie okresu, zamknięcie na koniec roku.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets"></a>Ulepszenia wydajności dotyczące ponownego kompilowania zestawów wymiarów finansowych
Nowa funkcja, która została dodana w wersji 10.0.16 poprawia wydajność procesów zamknięcia na koniec roku oraz konsolidacji. Funkcja nosi nazwę „Usprawnienia dotyczące wydajności do przebudowy zestawów wymiarów finansowych”. Ta funkcja zmienia sposób przebudowywania zestawów wymiarów, dzięki czemu są one przebudowywane tylko w odpowiednim horyzoncie czasowym. W poprzednich wersjach zestawy wymiarów były przebudowywane dla wszystkich dat. Jeśli na przykład zamykasz rok 2020, system przebuduje tylko salda transakcji z roku obrachunkowego 2020. Jeśli zostanie uruchomiona konsolidacja dla zakresu dat od 1 listopada 2020 r. do 30 listopada 2020 r., system dokona przebudowy jedynie sald z tego zakresu dat.

Aby używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego Zarządzanie funkcjami, aby sprawdzić stan funkcji i ją włączyć, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:
 
- Moduł: Księga główna
- Nazwa funkcji: Usprawnienia dotyczące wydajności do przebudowy zestawów wymiarów finansowych

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2021"></a>Rozrachunki z dostawcami: jakie zmiany zostały wprowadzone w celu zapewnienia obsługi raportów 1099 dotyczących końca roku dla roku 2021?

W roku 2021 formularze DIV, NEC i MISC zostały nieco zmienione i dodano w nich dodatkowe pola.

#### <a name="div-new-box2e-2f"></a>DIV: nowe pole 2e, 2f
 
- Pole 2e. Pokazuje część kwoty w polu 1a będącej przyrostem z sekcji 897, który został przypisany do dyspozycji amerykańskich udziałów w nieruchomościach (USRPI).  
- Pole 2f. Pokazuje część kwoty w polu 2a będącej przyrostem z sekcji 897, który został przypisany do dyspozycji USRPI. Należy zauważyć, że pola 2e i 2f dotyczą tylko obcokrajowców i jednostek, których dochód utrzymuje swoją specyfikę podczas przetwarzania przez lub dystrybucji do bezpośrednich lub pośrednich zagranicznych właścicieli lub beneficjentów. Na ogół jest traktowany jako skutecznie powiązany z handlem lub działalnością w Stanach Zjednoczonych. Zobacz instrukcje zwrotu podatku. 
 
#### <a name="nec-new-box-2"></a>NEC: nowe pole 2 
 
Jeśli pole 2 jest zaznaczone, należy raportować produkty konsumentów w łącznej kwocie minimum 5000 USD za produkty sprzedawane użytkownikom w celu odsprzedaży, na podstawie umowy kupna-sprzedaży, prowizji od przelewu lub na innej podstawie. Na ogół należy raportować wszelkie przychody ze sprzedaży tych produktów zgodnie z harmonogramem C (formularz 1040). 
 
Równocześnie uległ zmianie rozmiar formularza NEC. Podczas drukowania są dostępne trzy formularze na stronę. 
 
#### <a name="misc-new-box-11"></a>MISC: nowe pole 11 
 
Pole 11 zawiera kwotę zapłaconą za zakup ryb do odsprzedaży od każdej osoby zaangażowanej w handel rybami lub rybołówstwo. Zapoznaj się z instrukcjami zgłaszania tego przychodu w zeznaniach podatkowych. 
 
#### <a name="electronic-filing"></a>Przesyłanie dokumentów drogą elektroniczną 
Aby uzyskać informacje dotyczące przesyłania dokumentów drogą elektroniczną, zobacz [Publikacje dotyczące wymagań przesyłania dokumentów drogą elektroniczną](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

Aktualizuj specyfikacje formatu i układy rekordów dla raportu elektronicznego 2021 
- Sekcja 2 Rekord „A” wystawcy. 
- Kody kwot — zwiększona pozycja pola 28–45, długość do 18. 
 
#### <a name="sec-2-issuer-a-record-for-reporting-payments-on-form-1099-div"></a>Sekcja 2 Rekord „A” wystawcy, do raportowania płatności na formularzu 1099-DIV: 
- Typ kwoty – dodana sekcja 897 Zwykłe dywidendy i kod kwoty dodanej H. 
- Typ kwoty – dodana sekcja 897 Zyski kapitałowe i kod kwoty dodanej J. 
 
#### <a name="sec-3-payee-b-record"></a>Sekcja 3 Rekord „B” odbiorcy płatności 
- Rekordy informacji ogólnych — zaktualizowano trzeci punkt z 16 do 18 pól kwot płatności. 
- Płatność tytułu pola H — zaktualizowana nazwa stanowiska 247–258, tytuł pola, długość i ogólny opis pola. 
- Płatność tytułu pola J — zaktualizowana nazwa stanowiska 259–270, tytuł pola, długość i ogólny opis pola. 
- Zaktualizowano puste pole do pozycji pola 271–286. 
- Zaktualizowano wskaźnik kraju obcego do pozycji pola 287. 
- Zaktualizowano pole wiersza nazwy pierwszego odbiorcy płatności do pozycji pola 288–327. 
- Zaktualizowano pole wiersza nazwy drugiego odbiorcy płatności do pozycji pola 328–367. 
- Pozycje układu rekordu, formularz 1099-MISC — usunięto pozycję pola 548 i wskaźnik zapotrzebowania na składanie dokumentu FATCA w tytule pola. 
- Pozycje układu rekordu, formularz 1099-NEC — aktualizacja pola 545–546 na puste, aktualizacja pola 547 na wskaźnik sprzedaży bezpośredniej, długość i opis oraz uwagi, aktualizacja pola 548–722 na puste. 
 
#### <a name="sec-4-end-of-issuer-c-record"></a>Sekcja 4 Rekord „C” końca wystawcy 
- Płatność tytułu pola H — zaktualizowana nazwa stanowiska 304–321, tytuł pola, długość i ogólny opis pola. 
- Płatność tytułu pola J — zaktualizowana nazwa stanowiska 322–339, tytuł pola, długość i ogólny opis pola. 
- Nazwa tytułu 340–499 — długość zaktualizowana do 160. 
 
#### <a name="sec-5-state-totals-k-record"></a>Sekcja 5 Rekord „K” sum stanu 
- Płatność tytułu pola H — zaktualizowana nazwa stanowiska 304–321, tytuł pola, długość i ogólny opis pola. 
- Płatność tytułu pola J — zaktualizowana nazwa stanowiska 322–339, tytuł pola, długość i ogólny opis pola. 
- Nazwa tytułu 340–499 — długość zaktualizowana do 160.  

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Rozrachunki z dostawcami: 1099 — w jaki sposób zmienić pole i wartości dla dostawcy w formularzu 1099, który nie śledził informacji dotyczących podatku 1099 przez cały rok?
Użyj funkcji Aktualizacja formularza 1099 (**Rozrachunki z dostawcami > Dostawcy >Wszyscy dostawcy > Wybierz dostawcę > Karta Dostawca na wstążce > Aktualizacja formularza 1099**), aby przejrzeć transakcje z poprzednio zapłaconych faktur w celu ponownego odpowiedniego przypisania danych 1099 zgodnie z ustawieniami na karcie **Podatek 1099** na stronie **Dostawca**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>Czy można uruchomić funkcję Aktualizacja formularza 1099 dla wszystkich dostawców jednocześnie?
Nr Rutynowa procedura Aktualizacja formularza 1099 jest realizowana dla jednego dostawcy na raz. Jeśli ten wymóg ma zastosowanie do Twojej organizacji, polecamy zagłosować na koncepcję [Przetwarzanie partii aktualizacji danych 1099 dostawcy](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Rozrachunki z dostawcami: 1099 — Oblicz ponownie istniejące kwoty podatku 1099 a Aktualizuj wszystko w narzędziu Aktualizacja formularza 1099
W przypadku jego użycia w połączeniu z polem wyboru **Aktualizuj wszystko** zaznaczenie pola wyboru **Oblicz ponownie istniejące kwoty podatku 1099** spowoduje zresetowanie kwot podatku 1099 do łącznych zapłaconych wartości. 

[![Transakcje podatku 1099: przed uruchomieniem rutynowej procedury aktualizacji.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Pole wyboru **Oblicz ponownie istniejące kwoty podatku 1099** jest dostępne tylko wtedy, gdy istnieją faktura uwzględnia częściowe wartości podatku 1099 lub jeśli faktura została zmodyfikowana w formularzu podatku 1099. Załóżmy na przykład, że faktura jest wyceniona na 1000,00$, ale użytkownik wpisuje ręcznie w formularzu 1099 kwotę 500,00$ dla faktury.

[![Transakcje podatku 1099: zaznaczenie opcji Aktualizuj wszystko oraz Oblicz ponownie istniejące kwoty podatku 1099.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Gdy ta kwota zostanie zapłacona, kwotą zapłaconą na podstawie formularza 1099 będzie 500,00$. W przypadku przeprowadzania procedury ponownego obliczenia system zmieni kwotę w formularzu 1099 na 1000,00$, czyli łączną zapłaconą kwotę.

[![Transakcje podatku 1099: po uruchomieniu procedury 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Rozrachunki z dostawcami: 1099 — ręczne tworzenie transakcji 1099
Organizacja może wymagać ręcznego utworzenia transakcji 1099, które nie są skojarzone z fakturą. Ręczne transakcje 1099 można dodać, przechodząc do sekcji **Rozrachunki z dostawcami > Zadania okresowe > Podatek 1099 > Rozliczenia dostawcy dotyczące podatku 1099**. Wybierz przycisk **Ręczne transakcje podatku 1099**. 

Ręcznie utworzone transakcje dotyczące podatku 1099 nie są aktualizowane przy użyciu narzędzia **Aktualizuj wszystko** ani **Ponowne obliczanie istniejące kwoty podatku 1099** w narzędziu **Aktualizacja formularza 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Rozrachunki z dostawcami: 1099 — czy rozwiązanie Dynamics 365 Finance obsługuje formularz 1096? 

Rozwiązanie Dynamics 365 Finance nie umożliwia wydrukowania formularza 1096 Roczne podsumowanie i przekazywanie informacji zwrotnych w USA.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Rozrachunki z dostawcami: 1099 — czy są dostępne nowe funkcje do obsługi raportów 1099 dla sektora publicznego? 
**Aktualizacja danych formularza 1099 za pośrednictwem konta głównego** to nowa funkcja dla sektora publicznego, którą można włączyć w obszarze roboczym **Zarządzanie funkcjami**. Ta funkcja umożliwia powiązanie wartości formularza 1099 dla dostawcy za pośrednictwem konta głównego w obszarze podziału księgowań, a nie na domyślnym koncie w rekordzie dostawcy.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie dostawców dla raportowania 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
