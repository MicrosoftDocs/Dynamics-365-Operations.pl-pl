---
title: Zapisane widoki
description: W tym temacie opisano sposób korzystania z funkcji zapisanych widoków.
author: jasongre
manager: AnnBe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: c6a5880c6ae9470dbf7986f39798ec888d0c22ea
ms.sourcegitcommit: 1789a78de1cbeac19d96767812df653a191c67e9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2020
ms.locfileid: "3100315"
---
# <a name="saved-views"></a>Zapisane widoki

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="introduction"></a>Wprowadzenie
Personalizacja odgrywa ważną rolę w umożliwieniu użytkownikom i organizacjom optymalizacji doświadczenia użytkownika stosownie do ich potrzeb. Aby uzyskać szczegółowe informacje dotyczące personalizacji, zobacz [Dostosowanie do użytkownika](personalize-user-experience.md).

W przypadku tradycyjnej personalizacji użytkownicy mogą mieć tylko jeden zestaw personalizacji na formularz. Zapisane widoki rozwijają personalizację na kilka ważnych sposobów:

-    Widoki umożliwiają użytkownikom posiadanie więcej niż jednego nazwanego zestawu personalizacji na formularz i ich szybkie przełączanie stosownie do potrzeb. Umożliwia to użytkownikowi tworzenie wielu zoptymalizowanych widoków strony, z których każdy jest dostosowany do potrzeb wykonywania określonego zadania biznesowego. 

-    Widoki utworzone dla określonych typów stron mogą również zawierać filtry dodane przez użytkownika lub kryteria sortowania, które umożliwiają użytkownikom szybkie odtworzenie często filtrowanych zestawów danych. Więcej szczegółów znajduje się w sekcji [Jakie strony obsługują widoki](saved-views.md#what-pages-support-views). 

-    Widoki mogą być publikowane dla użytkowników w określonych rolach zabezpieczeń i określonych firmach. Dlatego każdy użytkownik, który ma określoną rolę i dostęp w określonej firmie, może uzyskać dostęp do tego widoku i korzystać z niego, nawet jeśli użytkownik ten może nie mieć możliwości jego spersonalizowania. Ta możliwość publikowania pozwala organizacjom na definiowanie firmowych, standardowych widoków zoptymalizowanych pod kątem ich działalności. Więcej informacji zawiera sekcja [Zarządzanie personalizacjami na poziomie organizacyjnym za pomocą widoków](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).

-    W przeciwieństwie do tradycyjnej personalizacji widoki nie są automatycznie zapisywane, gdy użytkownik wykonuje jawne personalizacje lub filtruje listę. Jawne zapisywanie jest wymagane w celu zapewnienia elastyczności w tworzeniu widoku przed dokonaniem zmian skojarzonych z tym widokiem lub po nim oraz zapobiegania przypadkowemu modyfikowaniu definicji przez filtry lub personalizacje, które nie są przeznaczone do długoterminowego użycia.  

-    Widoki można dodawać do obszarów roboczych jako kafelki, listy lub łącza. Dlatego filtrowany zbiór danych może być układany w obszarze roboczym, a użytkownicy mogą kojarzyć zbiór personalizacji, które są odpowiednie dla tego zbioru danych z kafelkiem lub łączem.

## <a name="switching-between-views"></a>Przełączanie między widokami
Po włączeniu widoków dla środowiska każda strona obsługująca widoki będzie zawierać zwinięty formant selektora widoków w górnej części formularza, w którym jest wyświetlana nazwa bieżącego widoku.  

Istnieją dwa warianty wielkości selektora widoków: 

-   **Duże selektory widoków**: strony z dobrze widoczną listą będą miały duży selektor widoków z kilku powodów. Co najważniejsze, większy selektor widoku wskazuje strony, na których widok może zawierać filtry zdefiniowane przez użytkownika. Ponieważ filtry są uwzględniane w widokach, większy selektor jest również uzasadniony tym, że nazwy widoków często stanowią najlepszy opis danych wyświetlanych na ekranie i można oczekiwać, że użytkownicy będą częściej przełączali widoki na stronach tych typów.  
 
-   **Małe selektory widoków**: wszystkie inne formularze pełnostronicowe (z wyjątkiem obszaru roboczego i pulpitu nawigacyjnego) będą miały mniejszy selektor widoku wyświetlany obok podpisu strony. Widoki na tych stronach zawierają tylko personalizacje (a nie filtry zdefiniowane przez użytkownika). Na tych stronach podpis formularza lub tytuł rekordu często są najważniejszymi informacjami w górnej części formularza. Mniejszy rozmiar odzwierciedla także mniejszą oczekiwaną częstotliwość przełączania widoku na tych stronach. 
 
Kliknięcie nazwy widoku powoduje otwarcie selektora widoku i wyświetlenie listy dostępnych widoków tej strony

-    **Widok standardowy**: **standardowy** widok strony (znany wcześniej jako widok **klasyczny**) jest widokiem niezależnym od systemu, w którym nie są stosowane żadne jawne personalizacje.
-    **Widoki osobiste**: widoki bez kłódki przedstawiają widoki osobiste danego użytkownika. Są to widoki utworzone przez tego użytkownika lub otrzymane przez niego od administratora.  
-    **Zablokowane widoki**: niektóre widoki (na przykład widok **standardowy** i wszystkie widoki opublikowane w roli) mają obok nich symbol kłódki w selektorze widoków. Ten symbol wskazuje, że nie można edytować tych widoków. Jednak niejawne personalizacje, które odzwierciedlają użycie strony, są zapisywane automatycznie. Te niejawne personalizacje obejmują zmianę szerokości kolumny siatki, rozwijanie lub zwijanie skróconej karty. Jeśli użytkownik ma uprawnienia do personalizacji, może jednak utworzyć widok osobisty oparty na zablokowanym widoku używając akcji **Zapisz jako**.
-    **Nowe widoki**: opublikowane widoki, które nie zostały jeszcze otwarte, są wyróżnione iskrą na lewo od nazwy widoku.  

Aby przełączyć się do innego widoku, najpierw należy otworzyć selektor widoku, a następnie wybrać widok, który ma zostać załadowany. 

## <a name="creating-and-modifying-views"></a>Tworzenie i modyfikowanie widoków
W przeciwieństwie do tradycyjnej personalizacji widoki nie są automatycznie zapisywane, gdy użytkownik wykonuje jawne personalizacje (lub filtruje listę). Do zapisania tych zmian w widoku wymagana jest jawna akcja. Zapewnia to użytkownikowi elastyczność w tworzeniu widoku przed dokonaniem zmian skojarzonych z tym widokiem lub po nim oraz zapobiega przypadkowemu modyfikowaniu definicji przez jednorazowe filtry lub personalizacje. Należy jednak pamiętać, że niejawne personalizacje (jak rozwinięcie lub zwinięcie skróconej karty lub zmiana szerokości kolumny siatki) są zapisywane automatycznie w bieżącym widoku, nawet jeśli jest on zablokowany. 

Aby mieć pewność, że bieżący stan widoku jest znany, w momencie rozpoczęcia wprowadzania zmian w widoku przez wykonanie jawnej personalizacji lub filtrowania obok nazwy bieżącego widoku jest wyświetlana gwiazdka, która wskazuje, że użytkownik przegląda niezapisaną, zmodyfikowaną wersję tego widoku.

Jeśli chcesz zapisać te zmiany, wykonaj następujące kroki.
1.  Wybierz nazwę widoku, aby otworzyć selektor widoku.
2.  Aby zmodyfikować istniejący widok:
     1. Wybierz opcję **Zapisz**. Należy zauważyć, że ta akcja nie jest dostępna w przypadku widoków zablokowanych. 
3.  Aby utworzyć nowy widok:
     1.    Wybierz opcję **Zapisz jako**. 
     2.    Wprowadź nazwę widoku i (opcjonalnie) opis.
     3.    Wybierz opcję **Zapisz**.

## <a name="changing-the-default-view"></a>Zmienianie domyślnego widoku
Widok domyślny to widok, który system będzie próbował otworzyć po pierwszym przejściu do strony. Powinien to być widok, który prawdopodobnie będzie najczęściej używany.  

Aby zmienić domyślny widok strony, wykonaj następujące czynności: 
1.  Przełącz się na widok, który jest używany jako domyślny. 
2.  Wybierz nazwę widoku, aby otworzyć selektor widoku. 
3.  Naciśnij przycisk **Więcej**, a następnie wybierz opcję **Przypnij jako domyślny**.  

Podczas tworzenia nowego widoku (przy użyciu akcji **Zapisz jako**) można też ustawić nowy widok jako domyślny, włączając opcję **Przypnij jako domyślny** przed zapisaniem widoku.

Należy zauważyć, że w niektórych przypadkach kwerenda skojarzona z domyślnym widokiem nie jest wykonywana w momencie przejścia do strony po raz pierwszy. Jeśli na przykład przechodzisz przez kafelek do strony, kwerenda kafelka zostanie wykonana niezależnie od kwerendy skojarzonej z domyślnym widokiem. Jeśli natomiast przejdziesz do strony, której widok standardowy już ma zdefiniowaną kwerendę, pierwotna kwerenda będzie wykonywana zamiast kwerendy domyślnego widoku. W takim przypadku podczas ładowania widoku zostanie wyświetlony komunikat informacyjny. Przełączanie widoków po załadowaniu strony powinno umożliwić wykonanie kwerendy widoku w oczekiwany sposób. Począwszy od wersji 10.0.10 aktualizacji Platform update 34, komunikat informacyjny będzie mieć osadzoną akcję umożliwiającą załadowanie kwerendy domyślnego widoku bezpośrednio.

## <a name="managing-personal-views"></a>Zarządzanie widokami osobistymi 
Okno dialogowe **Zarządzaj moimi widokami** zawiera podstawowe funkcje obsługi widoków osobistych i kolejności widoków w selektorze widoków. Jeśli chcesz otworzyć tę stronę, kliknij nazwę widoku, aby otworzyć menu rozwijane selektora widoków, wybierz opcję **Więcej**, a następnie wybierz opcję **Zarządzaj moimi widokami**.  

Dostępny zestaw akcji dla listy dostępnych widoków tej strony jest następujący.  
-    **Zmień widok domyślny**: aby wyróżniony widok został widokiem domyślnym tej strony, należy użyć opcji **Przypnij jako domyślny**.  
-    **Zmień kolejność widoków**: za pomocą akcji **Przenieś w górę** i **Przenieś w dół** można zmienić kolejność widoków na liście.  
-    **Zmień nazwę widoku**: akcja **Zmień nazwę** pozwala zmienić nazwę wyróżnionego widoku osobistego. W przypadku widoków zablokowanych ta akcja jest wyłączona. 
-    **Usuń widok**: akcja **Usuń** umożliwia trwałe usunięcie wyróżnionego widoku z danej strony. Jeśli widok został usunięty, nie można go odtworzyć.  

Zmiany wprowadzone w tym oknie dialogowym zaczną obowiązywać po naciśnięciu przycisku **Zapisz**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Zarządzanie personalizacjami na poziomie organizacyjnym za pomocą widoków
W tej sekcji opisano sposób pewne różnice w zarządzaniu personalizacją z i bez funkcji zapisanych widoków, co ułatwia zapoznanie się z zapisanymi widokami w celu usprawnienia zarządzania personalizacjami na poziomie organizacyjnym.

Bez widoków administratorzy musieli zastosować zestaw personalizacji strony do użytkownika lub grupy użytkowników za pomocą strony Personalizacja. Jeśli ci użytkownicy mieli uprawnienia do personalizacji, personalizacje zostały zastosowane do tej strony. Nie było jednak możliwe zakazanie użytkownikom dalszego personalizowania strony, czyli organizacja nie mogła sprawić, aby jej użytkownicy mieli spójny interfejs użytkownika. Jeśli dowolny z tych użytkowników nie miał uprawnień do personalizacji, personalizacje wysłane mu przez administratora nie były ładowane. Ponadto, jeśli w organizacji zostali zatrudnieni nowi użytkownicy, administratorzy musieli im ręcznie załadować zestaw personalizacji. Nie było automatycznego mechanizmu określania pewnego zestawu personalizacji, który powinien być dostępny dla użytkownika w danej roli.

Przy użyciu funkcji zapisanych widoków zarządzanie organizacyjne personalizacjami jest znacznie łatwiejsze, głównie ze względu na możliwość publikowania widoków w grupach użytkowników. Po opublikowaniu widoku każdy użytkownik, który ma jedną z zdefiniowanych ról zabezpieczeń ma dostęp do określonych firm, będzie mógł wyświetlać ten widok i korzystać z niego, nawet jeśli użytkownik ten może nie mieć możliwości jego spersonalizowania. Pomimo że każdy użytkownik ma kopię opublikowanego widoku, do której jest stosowane użycie strony (jawne personalizacje), żaden użytkownik nie może zapisać jawnych personalizacji lub aktualizacji kwerendy w opublikowanym widoku. Innymi słowy, opublikowane widoki są zablokowane. Ponadto, jeśli nowi użytkownicy mają przypisane role w firmach, dla których widoki zostały opublikowane, będą automatycznie widzieli widoki skojarzone z ich rolami i firmami. Administrator nie musi wykonywać żadnych dodatkowych działań. Administrator nie wymaga żadnych dodatkowych akcji. Podobnie, jeśli użytkownicy zmienią role w organizacji lub mają dostęp do różnych firm, mogą nie mieć już dostępu do widoków, które zostały wcześniej opublikowane. Administrator nie musi wykonywać żadnych dodatkowych działań.

Aktualizacje opublikowanego widoku mogą być łatwo dystrybuowane użytkownikom przez ponowne opublikowanie widoku do odpowiednich ról zabezpieczeń i firm.

Możliwość publikowania umożliwia organizacjom definiowanie standardowych widoków firmowych zoptymalizowanych pod kątem ich działalności skierowanych do użytkowników mających określone role zabezpieczeń.  

## <a name="publishing-views"></a>Publikowanie widoków
Podczas procesu publikowania można przypisać widoki do co najmniej jednej roli zabezpieczeń dla co najmniej jednej firmy. Dlatego każdy użytkownik, który ma dostęp do firmy i który jest przypisany do jednej z tych ról, może uzyskiwać dostęp do widoków i korzystać z nich, ale nie może ich edytować. Administratorzy systemu mają uprawnienia do akcji **Publikuj** w menu rozwijanym selektora widoku. Jednak inni zaufani użytkownicy w organizacji mogą mieć również dostęp do możliwości wyświetlania publikacji za pośrednictwem nowych ról **Administratora zapisanych widoków**.

Aby opublikować widok, należy wykonać następujące kroki: 
1.  Utwórz i zapisz osobistą kopię widoku, który chcesz opublikować. 
2.  Po załadowaniu tego widoku wybierz nazwę widoku, aby otworzyć menu rozwijane selektora widoków. 
3.  Naciśnij przycisk **Więcej**, a następnie wybierz opcję **Publikuj**. Zostanie otwarte okno dialogowe Publikowanie.  
4.  Wpisz nazwę i (opcjonalnie) opis widoku. Wpisaną nazwę użytkownicy otrzymujący ten widok będą widzieć w selektorach widoku. Nazwy opublikowanych widoków strony muszą być unikatowe. Nazwy publikowanych widoków nie mogą się powtarzać, nawet jeśli są stosowane do różnych list ról lub firm.
5.  Dodaj role zabezpieczeń odpowiadające użytkownikom, do których skierowany jest ten widok.
6. Dodaj firmy, dla których ten widok powinien być dostępny. 
7. [10.0.9/Aktualizacja Platform update 33 lub nowsza] określa, czy widok powinien być publikowany jako widok domyślny dla wybranych użytkowników. Ustawienie widoku jako domyślnego oznacza, że ten widok będzie widoczny dla użytkowników podczas następnego otwierania strony docelowej. Spowoduje to modyfikację widoku domyślnego dla tych użytkowników; Jednak użytkownicy nadal będą mogli zmieniać swój widok domyślny po zakończeniu publikowania.    
8.  Wybierz opcję **Publikuj**.

W niektórych środowiskach może upłynąć trochę czasu (do godziny), zanim użytkownicy zobaczą opublikowany widok.

## <a name="modifying-a-published-view"></a>Modyfikowanie opublikowanego widoku
Po opublikowaniu widoku może się okazać, że użytkownik chce wprowadzić zmiany w opublikowanym widoku. Chociaż nie można wprowadzać zmian w samych opublikowanych widokach, ponieważ są one zablokowane dla wszystkich użytkowników (w tym tych, którzy je opublikowali), to można ponownie opublikować widok, aby dokonać jego aktualizacji.  

Jeśli zmiany, które mają zostać wprowadzone do opublikowanego widoku, obejmują tylko parametry publikowania (nazwa i opis widoku lub role zabezpieczeń, dla których jest publikowany widok), należy wykonać następujące czynności: 
1.  Przełącz się na opublikowany widok z parametrami, które chcesz zaktualizować. 
2.  Wybierz opcję **Publikuj** z menu rozwijanego selektora widoku. 
3.  Wybierz opcję **Tak**, jeśli chcesz zaktualizować istniejący widok (lub **Nie**, jeśli chcesz go opublikować pod inną nazwą).
4.  Zaktualizuj nazwę, opis i/lub role zabezpieczeń tego widoku. 
5.  Wybierz opcję **Publikuj**. 
6.  [10.0.8/Aktualizacja Platform update 32 lub wcześniejsza] Jeśli zaktualizowano nazwę opublikowanego widoku, należy również usunąć opublikowany widok ze starą nazwą (więcej informacji znajduje się w sekcji **Zarządzanie opublikowanymi widokami**). 
7. [10.0.9/Aktualizacja Platform update 33 lub nowsza] Jeśli pierwotnie wybrano ten opublikowany widok jako widok domyślny, będzie on ponownie widokiem domyślnym dla tych użytkowników po ponownym opublikowaniu.  

Jeśli zmiany w publikowanym widoku obejmują modyfikację personalizacji lub filtrów skojarzonych z widokiem, należy wykonać następujące czynności: 
1.  Przełącz się na opublikowany widok, który chcesz zmodyfikować. 
2.  Zapisz kopię opublikowanego widoku, aby utworzyć lokalną wersję roboczą opublikowanego widoku. 
3.  Zmodyfikuj lokalną wersję roboczą zgodnie z wymaganiami.
4.  Opublikuj widok pod pierwotną nazwą. 

## <a name="managing-published-views"></a>Zarządzanie opublikowanymi widokami
Podobnie jak w przypadku zarządzania widokami osobistymi okno dialogowe **Zarządzaj moimi widokami** oferuje użytkownikom z uprawnieniami do publikowania podstawowe możliwości kontroli nad opublikowanymi widokami tej strony (oprócz ich widoków osobistych). Jeśli chcesz otworzyć tę stronę, wybierz nazwę widoku, aby otworzyć menu rozwijane selektora widoków, wybierz opcję **Więcej**, a następnie wybierz opcję **Zarządzaj moimi widokami**.

O ile karta **Moje widoki** z listą widoków osobistych jest widoczna dla wszystkich użytkowników, to karta **Opublikowane** z listą wszystkich opublikowanych widoków danej strony jest wyświetlana tylko użytkownikom z uprawnieniami do publikowania. Ponieważ widoki mogą być publikowane przez różnych użytkowników, ważne jest, aby każdy mógł zarządzać pełną listą opublikowanych widoków, niezależnie od tego, czy dany użytkownik faktycznie opublikował widok.

Dostępny zestaw akcji dla listy wszystkich opublikowanych widoków strony jest następujący. 

-    **Publikuj**: akcja **Publikuj** umożliwia ponowne opublikowanie widoku po zmianie parametrów publikowania (nazwa, opis, role zabezpieczeń).
-    **Usuń**: akcja **Usuń** umożliwia trwałe usunięcie opublikowanego widoku. Ta akcja powoduje usunięcie widoku dla wszystkich użytkowników w systemie. Usunięcie opublikowanych widoków zacznie obowiązywać po wybraniu przycisku **Zapisz**.

## <a name="frequently-asked-questions"></a>Często zadawane pytania
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Jak włączyć zapisane widoki w środowisku? 
Uwaga: funkcja **zapisanych widoków** wymaga włączenia systemu personalizacji w Finance and Operations. Jeśli personalizacja jest wyłączona dla całego środowiska, widoki zostaną wyłączone nawet po wykonaniu poniższych kroków. 

**10.0.9/Aktualizacja platformy 33 i późniejsza** Funkcja **zapisanych widoków** jest dostępna bezpośrednio w module Zarządzanie funkcjami w dowolnym środowisku. Podobnie jak inne funkcje prapremiery publicznej, włączenie tej funkcji w produkcji podlega [uzupełniającemu warunkowi stosowania Umowy](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8/Aktualizacja platformy 32 i wcześniejsza** Funkcja **zapisanych widoków** można włączyć w środowiskach warstwy 1 (Dev/Test) i warstwa 2 (piaskownicy) w celu zapewnienia dodatkowych zmian w testowaniu i projekcie, wykonując poniższe kroki.

1.  **Włącz funkcję testową**: wykonaj następującą instrukcję SQL: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLISavedViewsEnableFeature', 1, 0, 5637144576);`

2. **Zresetuj usługi IIS**, aby opróżnić statyczną dystrybucję testową pamięci podręcznej. 

3.  **Znajdź funkcję**: przejdź do obszaru roboczego **Zarządzanie funkcjami**. Jeśli **Zapisane widoki** nie są wyświetlane na liście, wybierz przycisk **Sprawdź aktualizacje**.   

4.  **Włącz funkcję**: Znajdź funkcję **Zapisane widoki** na liście funkcji i wybierz przycisk **Włącz teraz** w okienku szczegółów.

Wszystkie kolejne sesje użytkownika będą uruchamiane z włączonymi zapisanymi widokami.


### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Co się dzieje z istniejącymi personalizacjami, gdy są włączone widoki? 
Po włączeniu widoków wszelkie istniejące personalizacje użytkownika i formularza są zapisywane w nowym widoku o nazwie **Mój widok**, który jest automatycznie ustawiany jako widok domyślny. Ma to na celu zapewnienie spójnego środowiska użytkownika przed włączeniem widoków i po nim, z wyjątkiem formantu selektora widoków wyświetlanego w formularzach.  

### <a name="what-pages-support-views"></a>Jakie strony obsługują widoki? 
Widoki są dostępne dla większości, ale nie wszystkich stron. Dokładnie rzecz biorąc, widoki są obecnie dostępne na wszystkich stronach pełnoekranowych, z wyjątkiem pulpitów nawigacyjnych i obszarów roboczych. Strony niepełnoekranowe, zawierające okna dialogowe, okna dialogowe rozwijane, wyszukiwania, rozszerzone podglądy, obecnie nie obsługują widoków. Obsługa widoków na dodatkowych stronach, jak obszary robocze i okna dialogowe, być może zostanie dodana w przyszłej aktualizacji.   

### <a name="who-is-allowed-to-publish-views"></a>Kto ma prawo do publikowania widoków?
Tylko administratorzy systemu i użytkownicy przypisani do roli **Administratora zapisanych widoków** mają prawa do publikowania widoków. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Dlaczego nie można zapisać filtrów w widoku? 
Istnieje kilka przyczyn uniemożliwiających zapisanie filtru w widoku: 

- Strona może nie obsługiwać zapisywania filtrów w ramach definicji widoku. Tylko strony z dużymi selektorami widoku umożliwiają zapisywanie personalizacji i modyfikacji kwerend w postaci widoku. Więcej informacji znajduje się w sekcji **Przełączanie widoków**. 

- Ta strona może nie obsługiwać poprawnie widoków, ponieważ może całkowicie zignorować kwerendę widoku lub może działać na tymczasowej tabeli, której dane nie są trwałe. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Jakie dane są widoczne podczas odwiedzania strony? 
W przypadku stron z niewielkimi selektorami widoku (w widoku można zapisywać tylko personalizacje), podczas odwiedzania strony będą widoczne te same dane. 

W przypadku stron z dużymi selektorami widoku (personalizacje i kwerendy mogą być zapisywane w widoku) zostaną wyświetlone głównie dane połączone z kwerendą skojarzoną z widokiem domyślnym. Są od tego dwa wyjątki: — Jeśli przejdziesz do strony z kafelka, kwerenda kafelka zostanie wykonana niezależnie od kwerendy skojarzonej z domyślnym widokiem. Jeśli utworzono ten kafelek po włączeniu widoków, zaznaczenie kafelka spowoduje otwarcie strony z widokiem skojarzonym z tym kafelkiem.   
     - Jeśli przejdziesz do strony i ten punkt wejścia zawiera kwerendę, pierwotna kwerenda będzie początkowo wykonywana zamiast kwerendy domyślnego widoku. W takim przypadku podczas ładowania widoku zostanie wyświetlony komunikat informacyjny. Można to również potwierdzić, przełączając się do tego widoku po załadowaniu strony, ponieważ wtedy kwerenda widoku powinna zostać bezwzględnie wykonana.  


