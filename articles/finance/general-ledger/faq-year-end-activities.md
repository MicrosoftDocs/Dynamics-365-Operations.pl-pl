---
title: Działania na koniec roku — często zadawane pytania
description: Ten temat został opracowany z myślą o ułatwieniu realizacji działań związanych z zamknięciem roku.
author: kweekley
manager: tfehr
ms.date: 01/25/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6d10f54913ca8dff56a59ea597a9bd7c3e69d4bc
ms.sourcegitcommit: bd4763cc6088e114818e80bb1c27c6521b039743
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5107702"
---
# <a name="year-end-activities-faq"></a>Działania na koniec roku — często zadawane pytania 

Ten temat został opracowany z myślą o ułatwieniu realizacji działań związanych z zamknięciem roku. Informacje zawarte w tym temacie skupiają się głównie wokół pytań dotyczących działań związanych z zamknięciem roku w obszarach Księga główna i Rozrachunki z dostawcami.

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Księga główna: skąd wiadomo, że proces zamknięcia na koniec roku jest uruchamiany, a nie wycofywany?
Wielokrotnie spotykaliśmy się z sytuacją, gdy organizacja próbuje uruchomić zamknięcie na koniec roku, zamiast tego dokonuje jednak cofnięcia zamknięcia na koniec roku. Jeśli zamknięcie na koniec roku nastąpi bardzo szybko albo nie spowoduje wygenerowania sald otwarcia, sprawdź ustawienie **Cofnij poprzednie zamknięcie** w obszarze **Zamknięcie na koniec roku** (**Księga główna > Zamknięcie okresu > Zamknięcie na koniec roku > Uruchom zamknięcie obrachunkowe**). 

[![Uruchamianie i cofanie procesu zamknięcia na koniec roku](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Jeśli dla funkcji **Cofnij poprzednie zamknięcie** wybrano opcję **Tak**, poprzednie zamknięcie na koniec roku zostanie cofnięte. W przypadku uruchomienia operacji cofnięcia wszystkie wpisy salda zamknięcia i salda otwarcia zostaną usunięte, tak jakby zamknięcie na koniec roku nigdy nie zostało uruchomione. Załączniki zostaną usunięte. Zamknięcie na koniec roku nie zostanie ponownie uruchomione automatycznie. Konieczne będzie ponowne rozpoczęcie procesu, przy czym tym razem należy dla opcji **Cofnij poprzednie zamknięcie** wybrać ustawienie **Nie**. 

> [!NOTE]
> Wpis salda zamknięcia jest opcjonalnie tworzony w zamykanym roku. Dzieje się tak tylko wtedy, gdy parametr księgi głównej **Tworzenie transakcji zamknięcia podczas transferu** ma wartość **Tak**. Wpis salda otwarcia jest tworzony zawsze, ponieważ jest to saldo początkowe dla następnego roku.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Księga główna: jaka jest różnica między parametrami księgi głównej Cofnij i Usuń dla zamknięcia na koniec roku?
Istnieją dwie pozycje, które ze względu na pewne podobieństwo mogą się mylić. Warto zwrócić uwagę na różnice między nimi. **Cofnij poprzednie zamknięcie** to funkcja dostępna z poziomu okna dialogowego **Zamknięcie na koniec roku**, natomiast **Usuwanie transakcji zamknięcia roku podczas przenoszenia** to parametr księgi głównej (**Księga główna > Zamknięcie okresu > Zamknięcie na koniec roku > Uruchom zamknięcie obrachunkowe**).  

[![Różnica między funkcją Cofnij a parametrem księgi głównej Usuń dla zamknięcia na koniec roku](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Wybierz polecenie **Cofnij poprzednie zamknięcie** w rozwijanym menu dialogowym podczas uruchamiania procesu zamknięcia na koniec roku, aby usunąć wszystkie wpisy salda zamknięcia i salda otwarcia, tak jakby zamknięcie na koniec roku nigdy nie zostało uruchomione. Załączniki zostaną usunięte. Zamknięcie na koniec roku nie zostanie ponownie uruchomione automatycznie. Aby uruchomić zamknięcie na koniec roku, należy ponownie zainicjować ten proces, tym razem zmieniając ustawienie funkcji **Cofnij poprzednie zamknięcie** na **Nie** (**Księga główna > Ustawienia księgi > Parametry księgi głównej**). 

[![Ustawienie parametru księgi głównej](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

Parametr **Usuwanie transakcji zamknięcia roku podczas przenoszenia** w księdze głównej jest używana tylko w przypadku uruchamiania (a nie wycofywania) zamknięcia na koniec roku (opcja **Cofnij poprzednie zamknięcie** ma ustawienie **Nie**). Jeśli ten parametr ma wartość **Tak**, wszystkie wpisy salda zamknięcia i salda otwarcia zostaną usunięte, a zamknięcie na koniec roku zostanie ponownie uruchomione. Ten proces stosuje się, gdy organizacja chce, aby wszystkie transakcje, w tym korekty od ostatniego zamknięcia na koniec roku, zastały zaksięgowane w jednym wpisie księgowania dla wpisów salda zamknięcia i salda otwarcia. 

Jeśli ta opcja ma wartość **Nie**, wszystkie wpisy salda zamknięcia i salda otwarcia zostaną pozostawione. Nie zostaną one usunięte. Zamiast tego zostanie utworzony nowy wpis salda zamknięcia i salda otwarcia jedynie dla różnicy albo dla nowych transakcji zaksięgowanych od ostatniego zamknięcia na koniec roku mającego miejsce w danym roku obrachunkowym.  

> [!NOTE]
> Wpis salda zamknięcia jest tworzony w zamykanym roku. Dzieje się tak tylko wtedy, gdy parametr **Tworzenie transakcji zamknięcia podczas transferu** w księdze głównej ma wartość **Tak**. Wpis salda otwarcia jest tworzony zawsze, ponieważ jest to saldo początkowe dla następnego roku. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Księga główna: co można zmienić, aby zwiększyć wydajność przetwarzania na koniec roku? 
W celu poprawy wydajności zamknięcia na koniec roku można wprowadzić wiele zmian. Zalecamy rozważenie sugerowanych zmian w celu podjęcia decyzji w kwestii tego, czy są one odpowiednie dla organizacji.  

### <a name="dimension-sets"></a>Zestawy wymiarów
Podczas uruchamiania procesu zamknięcia na koniec roku następuje przebudowa sald poszczególnych zestawów wymiarów, co ma bezpośredni wpływ na wydajność. Niektóre organizacje tworzą zestawy wymiarów niepotrzebnie, tylko dlatego, że były one używane w przeszłości lub mogły zostać kiedyś użyte.  Te niepotrzebne zestawy wymiarów są dalej przebudowywane podczas realizacji procesu zamknięcia na koniec roku, co wydłuża czas jego trwania. Poświęć nieco czasu na ocenę zestawów wymiarów i usunięcie tych z nich, które nie są potrzebne.

Zbędne zestawy wymiarów wpływają również na przebieg zadania wsadowego **BudgetDimensionFocusInitializeBalance** (**Księga główna > Plan kont > Wymiary > Zestawy wymiarów finansowych**).

[![Zestawy wymiarów finansowych](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Konfiguracja szablonu zamknięcia na koniec roku
Szablon zamknięcia na koniec roku pozwala organizacjom wybrać poziom wymiaru finansowego do obsługi podczas przenoszenia sald kont wynikowych do wstrzymanych dochodów. Ustawienia umożliwiają organizacji obsługę szczegółowych wymiarów finansowych (**Zamknij wszystko**) podczas przenoszenia sald do wstrzymanych dochodów lub podjęcie decyzji o podsumowaniu kwot w ramach wartości jednego wymiaru (**Zamknij jeden**). Możliwe jest jego zdefiniowanie dla każdego wymiaru finansowego. Aby uzyskać więcej informacji dotyczących tych ustawień, zobacz temat [Zamknięcie na koniec roku](year-end-close.md).

Zalecamy ocenę wymagań organizacji i, jeśli to możliwe, zamknięcie możliwie wielu wymiarów za pomocą opcji **Zamknij jeden** dotyczącej końca roku, aby poprawić wydajność. Po zamknięciu wartości (która może być także wartością pustą) jednego wymiaru system określa mniej szczegółów podczas ustalania sald dla wpisów na koncie wstrzymanych dochodów.

### <a name="10013-update-or-later"></a>Aktualizacja 10.0.13 lub nowsza
Jeśli od czasu uruchomienia w organizacji ostatniego zamknięcia na koniec roku użytkownik dokonał aktualizacji do wersji 10.0.13 lub nowszej, proces zamknięcia na koniec roku może potrwać dłużej z powodu [implementacji funkcji skrótów w wersji 2](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/verify-hash-function-changes-after-update-to-dynamics-365-finance-2020-release-wave-2). (Termin *„skrót”* odnosi się do pola obliczonego na podstawie innych pól tekstowych. Interfejs API służący do obliczania wartości globalnie unikatowego identyfikatora (GUID) skrótu został zaktualizowany w celu zwiększenia poziomu bezpieczeństwa). Aby przyspieszyć proces zamykania na koniec roku, zaleca się przebudowanie sald zestawów wymiarów przed uruchomieniem zamknięcia na koniec roku. Jeśli przeprowadzono już przebudowę sald zestawu wymiarów po aktualizacji 10.0.13, nie jest konieczne ponowne uruchomienie procesu przebudowy.
 
## <a name="general-ledger--what-does-the-period-close--year-end-close-do"></a>Księga główna — jakie są skutki zamknięcia okresu / zamknięcia na koniec roku?
 
[![Zamknięcie okresu, zamknięcie na koniec roku](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets-new-feature"></a>Usprawnienia dotyczące wydajności do przebudowy zestawów wymiarów finansowych (nowa funkcja)
Nowa funkcja dodana w wersji 10.0.16 poprawia wydajność procesów zamknięcia na koniec roku oraz konsolidacji. Funkcja nosi nazwę „Usprawnienia dotyczące wydajności do przebudowy zestawów wymiarów finansowych”. Ta funkcja zmienia sposób przebudowywania zestawów wymiarów, dzięki czemu są one przebudowywane tylko w odpowiednim horyzoncie czasowym. W poprzednich wersjach zestawy wymiarów były przebudowywane dla wszystkich dat. Jeśli na przykład zamykasz rok 2020, system przebuduje tylko salda transakcji z roku obrachunkowego 2020. Jeśli zostanie uruchomiona konsolidacja dla zakresu dat od 1 listopada 2020 r. do 30 listopada 2020 r., system dokona przebudowy jedynie sald z tego zakresu dat.

Jako wprowadzenie tej funkcji jest traktowane jako zmiana powodująca niezgodność, funkcję tę należy włączyć w obszarze roboczym **Zarządzanie funkcjami**.
 
[![Zamknięcie na koniec roku](./media/faq-2020-yr-end-06.png)](./media/faq-2020-yr-end-06.png)

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2020"></a>Rozrachunki z dostawcami: jakie zmiany zostały wprowadzone w celu zapewnienia obsługi raportów 1099 dotyczących końca roku dla roku 2020?

W 2020 roku zostały wprowadzone dwie nowe funkcje wymagane przepisami prawa i dotyczące zmian w zakresie raportów 1099 dotyczących końca roku. Pierwsza funkcja, **Zastosuj zmiany do formularzy 1099-NEC i 1099-MISC na rok 2020**, została wprowadzona w ciągu roku jako funkcja obowiązkowa. Jej celem jest zapewnienie, że dane transakcji 1099 dla roku 2020 mogą być śledzone na potrzeby nowego formularza 1099-NEC. Ta funkcja dodaje pola formularza 1099, które są potrzebne do obsługi pól nowych formularzy 1099-NEC i zaktualizowanych formularzy 1099-MISC. Ta aktualizacja pozwoliła także uaktualnić dane rekordu dostawcy stanowiące informacje podawane w polu formularza 1099. 

Druga funkcja wymagana przepisami prawa, **Deklaracje 1099 zaktualizowane pod kątem prawa podatkowego na rok 2020**, obejmuje zmiany wymienione poniżej.

- 1099-OID — urząd skarbowy przekonwertował formularz na potrzeby użytku ciągłego.
   - Trzecia i czwarta cyfra roku raportowania musi zostać wypełniona przed drukowaniem. Użyj trzeciej i czwartej cyfry **roku sprawozdawczego** z obszaru **Opcje drukowania podatku 1099**. 

- 1099-NEC — nowy formularz na rok 2020. Pozwala zarejestrować wynagrodzenia dla osoby, która nie ma statusu pracownika etatowego. 

-   1099-MISC — w związku z utworzeniem formularza 1099-NEC urząd skarbowy poprawił formularz 1099-MISC i dokonał zmiany numerów pól do zgłaszania określonych rodzajów przychodów.
Poniżej wymieniono zmiany w zakresie raportowania przychodów oraz numerowania pól formularza.
   - Płatnik dokonał bezpośredniej sprzedaży, której wartość wynosi co najmniej 5000$ (pole wyboru) — zgłoszenia dokonuje się w polu 7.
   - Wpływy z ubezpieczenia upraw są zgłaszane w polu 9.
   - Przychody brutto wypłacane prawnikom są zgłaszane w polu 10.
   - Odroczenia wynikające z sekcji 409A są zgłaszane w polu 12.
   - Niekwalifikujący się odroczony dochód z wynagrodzenia jest zgłaszany w polu 14.
   - Pola 15, 16 i 17 służą do raportowania odpowiednio potrąceń na podatki, krajowego numer identyfikacyjnego i kwoty dochodu uzyskanego w kraju.

- Brak zmian w formularzu 1099-DIV i 1099-INT w 2020 roku.

- Przesyłanie dokumentów drogą elektroniczną — format został zmieniony i dostosowany do rozmiarów nowego formularza NEC; wprowadzone zmiany pól formularza MISC opisano powyżej. Aby uzyskać szczegółowe informacje o wymaganiach dotyczących przesyłania dokumentów drogą elektroniczną, zobacz [publikację 1220 urzędu skarbowego](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Rozrachunki z dostawcami: 1099 — w jaki sposób zmienić pole i wartości dla dostawcy w formularzu 1099, który nie śledził informacji dotyczących podatku 1099 przez cały rok?
Użyj funkcji Aktualizacja formularza 1099 (**Rozrachunki z dostawcami > Dostawcy >Wszyscy dostawcy > Wybierz dostawcę > Karta Dostawca na wstążce > Aktualizacja formularza 1099**), aby przejrzeć transakcje z poprzednio zapłaconych faktur w celu ponownego odpowiedniego przypisania danych 1099 zgodnie z ustawieniami na karcie **Podatek 1099** na stronie **Dostawca**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>Czy można uruchomić funkcję Aktualizacja formularza 1099 dla wszystkich dostawców jednocześnie?
Nr Rutynowa procedura Aktualizacja formularza 1099 jest realizowana dla jednego dostawcy na raz. Jeśli ten wymóg ma zastosowanie do Twojej organizacji, polecamy zagłosować na koncepcję [Proces wsadowy aktualizacji danych 1099 dostawcy](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-vs-update-all-in-the-update-1099-utility"></a>Rozrachunki z dostawcami: 1099 — „Oblicz ponownie istniejące kwoty podatku 1099” a „Aktualizuj wszystko” w narzędziu Aktualizacja formularza 1099.
W przypadku jego użycia w połączeniu z polem wyboru **Aktualizuj wszystko** zaznaczenie pola wyboru **Oblicz ponownie istniejące kwoty podatku 1099** spowoduje zresetowanie kwot podatku 1099 do łącznych zapłaconych wartości. 

[![Transakcje podatku 1099: przed uruchomieniem rutynowej procedury aktualizacji](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Pole wyboru **Oblicz ponownie istniejące kwoty podatku 1099** jest dostępne tylko wtedy, gdy istnieją faktura uwzględnia częściowe wartości podatku 1099 lub jeśli faktura została zmodyfikowana w formularzu podatku 1099. Załóżmy na przykład, że faktura jest wyceniona na 1000,00$, ale użytkownik wpisuje ręcznie w formularzu 1099 kwotę 500,00$ dla faktury.

[![Transakcje podatku 1099: zaznaczenie opcji Aktualizuj wszystko oraz Oblicz ponownie istniejące kwoty podatku 1099](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Gdy ta kwota zostanie zapłacona, kwotą zapłaconą na podstawie formularza 1099 będzie 500,00$. W przypadku przeprowadzania procedury ponownego obliczenia system zmieni kwotę w formularzu 1099 na 1000,00$, czyli łączną zapłaconą kwotę.

[![Transakcje podatku 1099: po uruchomieniu procedury 1099](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Rozrachunki z dostawcami: 1099 — ręczne tworzenie transakcji 1099
Organizacja może wymagać ręcznego utworzenia transakcji 1099, które nie są skojarzone z fakturą. Ręczne transakcje 1099 można dodać, przechodząc do sekcji **Rozrachunki z dostawcami > Zadania okresowe > Podatek 1099 > Rozliczenia dostawcy dotyczące podatku 1099**. Wybierz przycisk **Ręczne transakcje podatku 1099**. 

Ręcznie utworzone transakcje dotyczące podatku 1099 nie są aktualizowane przy użyciu narzędzia **Aktualizuj wszystko** ani **Ponowne obliczanie istniejące kwoty podatku 1099** w narzędziu **Aktualizacja formularza 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Rozrachunki z dostawcami: 1099 — czy Dynamics 365 Finance obsługuje formularz 1096? 

Program Dynamics 365 Finance nie umożliwia wydrukowania formularza 1096 „Roczne podsumowanie i przekazywanie informacji zwrotnych w USA”.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Rozrachunki z dostawcami: 1099 — czy są dostępne nowe funkcje do obsługi raportów 1099 dla sektora publicznego? 
**Aktualizacja danych formularza 1099 za pośrednictwem konta głównego** to nowa funkcja dla sektora publicznego, którą można włączyć w obszarze roboczym **Zarządzanie funkcjami**. Ta funkcja umożliwia powiązanie wartości formularza 1099 dla dostawcy za pośrednictwem konta głównego w obszarze podziału księgowań, a nie na domyślnym koncie w rekordzie dostawcy.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie dostawców dla raportowania 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).
