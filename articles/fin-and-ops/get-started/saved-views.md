---
title: Zapisane widoki
description: W tym temacie opisano sposób korzystania z funkcji zapisanych widoków.
author: jasongre
manager: AnnBe
ms.date: 08/01/2019
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
ms.openlocfilehash: 43f25796e6271f14acfc72f931398ab63338a307
ms.sourcegitcommit: b068b17ef708a0b349db8df1542e4244bb983d13
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2019
ms.locfileid: "1870840"
---
# <a name="saved-views"></a>Zapisane widoki

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="introduction"></a>Wprowadzenie
Personalizacja odgrywa ważną rolę w umożliwieniu użytkownikom i organizacjom optymalizacji doświadczenia użytkownika w programie Microsoft Dynamics 365 for Finance and Operations stosownie do ich potrzeb. Aby uzyskać szczegółowe informacje dotyczące personalizacji, zobacz [Dostosowanie do użytkownika](personalize-user-experience.md).

W przypadku tradycyjnej personalizacji użytkownicy mogą mieć tylko jeden zestaw personalizacji na formularz. Zapisane widoki rozwijają personalizację na kilka ważnych sposobów:

-    Widoki umożliwiają użytkownikom posiadanie więcej niż jednego nazwanego zestawu personalizacji na formularz i ich szybkie przełączanie stosownie do potrzeb. Umożliwia to użytkownikowi tworzenie wielu zoptymalizowanych widoków strony, z których każdy jest dostosowany do potrzeb wykonywania określonego zadania biznesowego. 

-    Widoki utworzone dla określonych typów stron mogą również zawierać filtry dodane przez użytkownika lub kryteria sortowania, które umożliwiają użytkownikom szybkie odtworzenie często filtrowanych zestawów danych. Więcej szczegółów znajduje się w sekcji [Jakie strony obsługują widoki](saved-views.md#what-pages-support-views). 

-    Widoki można publikować w rolach zabezpieczeń, co oznacza, że każdy użytkownik mający taką rolę będzie mógł uzyskać dostęp do tego widoku i korzystać z niego, niezależnie od dostępności funkcji personalizacji dla użytkownika. Ta możliwość publikowania pozwala organizacjom na definiowanie standardowych widoków firmowych zoptymalizowanych pod kątem ich działalności. Więcej informacji zawiera sekcja [Zarządzanie personalizacjami na poziomie organizacyjnym za pomocą widoków](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).

-    W przeciwieństwie do tradycyjnej personalizacji widoki nie są automatycznie zapisywane, gdy użytkownik wykonuje jawne personalizacje lub filtruje listę. Jawne zapisywanie jest wymagane w celu zapewnienia elastyczności w tworzeniu widoku przed dokonaniem zmian skojarzonych z tym widokiem lub po nim oraz zapobiegania przypadkowemu modyfikowaniu definicji przez filtry lub personalizacje, które nie są przeznaczone do długoterminowego użycia.  

## <a name="switching-between-views"></a>Przełączanie między widokami
Po włączeniu widoków dla środowiska każda strona obsługująca widoki będzie zawierać zwinięty formant selektora widoków w górnej części formularza, w którym jest wyświetlana nazwa bieżącego widoku.  

Istnieją dwa warianty wielkości selektora widoków: 

-   **Duże selektory widoków**: strony z dobrze widoczną listą będą miały duży selektor widoków z kilku powodów. Co najważniejsze, większy selektor widoku wskazuje strony, na których widok może zawierać filtry zdefiniowane przez użytkownika. Ponieważ filtry są uwzględniane w widokach, większy selektor jest również uzasadniony tym, że nazwy widoków często stanowią najlepszy opis danych wyświetlanych na ekranie i można oczekiwać, że użytkownicy będą częściej przełączali widoki na stronach tych typów.  
 
-   **Małe selektory widoków**: wszystkie inne formularze pełnostronicowe (z wyjątkiem obszaru roboczego i pulpitu nawigacyjnego) będą miały mniejszy selektor widoku wyświetlany obok podpisu strony. Widoki na tych stronach zawierają tylko personalizacje (a nie filtry zdefiniowane przez użytkownika). Na tych stronach podpis formularza lub tytuł rekordu często są najważniejszymi informacjami w górnej części formularza. Mniejszy rozmiar odzwierciedla także mniejszą oczekiwaną częstotliwość przełączania widoku na tych stronach. 
 
Kliknięcie nazwy widoku powoduje otwarcie selektora widoku i wyświetlenie listy dostępnych widoków tej strony

-    **Widok klasyczny**: widok klasyczny jest gotowym widokiem strony bez zastosowania jawnych personalizacji.  
-    **Widoki osobiste**: widoki bez kłódki przedstawiają widoki osobiste danego użytkownika. Są to widoki utworzone przez tego użytkownika lub otrzymane przez niego od administratora.  
-    **Zablokowane widoki**: niektóre widoki (takie jak widok klasyczny i wszystkie widoki opublikowane w roli) są opatrzone kłódką w selektorze widoku, co oznacza, że nie można ich edytować. Jednak niejawne personalizacje dotyczące użycia strony są zapisywane automatycznie, np. zmiana szerokości kolumny siatki lub rozwijanie lub zwijanie skróconej karty. Można jednak utworzyć widok osobisty oparty na zablokowanym widoku, używając akcji **Zapisz kopię**, jeśli użytkownik ma uprawnienia do personalizacji.
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
     1.    Naciśnij przycisk **Zapisz kopię**. 
     2.    Wprowadź nazwę widoku i (opcjonalnie) opis.
     3.    Wybierz opcję **Zapisz**.

## <a name="changing-the-default-view"></a>Zmienianie domyślnego widoku
Widok domyślny to widok, który system będzie próbował otworzyć po pierwszym przejściu do strony. Powinien to być widok, który prawdopodobnie będzie najczęściej używany.  

Aby zmienić domyślny widok strony, wykonaj następujące czynności: 
1.  Przełącz się na widok, który jest używany jako domyślny. 
2.  Wybierz nazwę widoku, aby otworzyć selektor widoku. 
3.  Naciśnij przycisk **Więcej**, a następnie wybierz opcję **Przypnij jako domyślny**.  

Podczas tworzenia nowego widoku (przy użyciu akcji **Zapisz kopię**) można też ustawić nowy widok jako domyślny, włączając opcję **Przypnij jako domyślny** przed zapisaniem widoku.  

Należy zauważyć, że w niektórych przypadkach kwerenda skojarzona z domyślnym widokiem nie jest wykonywana w momencie przejścia do strony po raz pierwszy. Jeśli na przykład przechodzisz przez kafelek do strony, kwerenda kafelka zostanie wykonana niezależnie od kwerendy skojarzonej z domyślnym widokiem. Jeśli natomiast przejdziesz do strony, której widok klasyczny już ma zdefiniowaną kwerendę, pierwotna kwerenda będzie początkowo wykonywana zamiast kwerendy domyślnego widoku. W takim przypadku podczas ładowania widoku zostanie wyświetlony komunikat informacyjny. Przełączanie widoków po załadowaniu strony powinno umożliwić wykonanie kwerendy widoku w oczekiwany sposób.

## <a name="managing-personal-views"></a>Zarządzanie widokami osobistymi 
Okno dialogowe **Zarządzaj moimi widokami** zawiera podstawowe funkcje obsługi widoków osobistych i kolejności widoków w selektorze widoków. Jeśli chcesz otworzyć tę stronę, kliknij nazwę widoku, aby otworzyć menu rozwijane selektora widoków, wybierz opcję **Więcej**, a następnie wybierz opcję **Zarządzaj moimi widokami**.  

Dostępny zestaw akcji dla listy dostępnych widoków tej strony jest następujący.  
-    **Zmień widok domyślny**: aby wyróżniony widok został widokiem domyślnym tej strony, należy użyć opcji **Przypnij jako domyślny**.  
-    **Zmień kolejność widoków**: za pomocą akcji **Przenieś w górę** i **Przenieś w dół** można zmienić kolejność widoków na liście.  
-    **Zmień nazwę widoku**: akcja **Zmień nazwę** pozwala zmienić nazwę wyróżnionego widoku osobistego. W przypadku widoków zablokowanych ta akcja jest wyłączona. 
-    **Usuń widok**: akcja **Usuń** umożliwia trwałe usunięcie wyróżnionego widoku z danej strony. Jeśli widok został usunięty, nie można go odtworzyć.  

Zmiany wprowadzone w tym oknie dialogowym zaczną obowiązywać po naciśnięciu przycisku **Zapisz**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Zarządzanie personalizacjami na poziomie organizacyjnym za pomocą widoków
Aby zrozumieć udoskonalenia zarządzania personalizacjami na poziomie organizacyjnym, najpierw zapoznaj się z działaniem zarządzania personalizacjami bez widoków.  

Bez widoków administratorzy musieli zastosować zestaw personalizacji strony do użytkownika lub grupy użytkowników za pomocą strony Personalizacja. Jeśli ci użytkownicy mieli uprawnienia do personalizacji, personalizacje zostały zastosowane do tej strony. Nie było jednak możliwe zakazanie użytkownikom dalszego personalizowania strony, czyli organizacja nie mogła sprawić, aby jej użytkownicy mieli spójny interfejs użytkownika. Jeśli dowolny z tych użytkowników nie miał uprawnień do personalizacji, personalizacje wysłane mu przez administratora nie były ładowane. Ponadto, jeśli w organizacji zostali zatrudnieni nowi użytkownicy, administratorzy musieli im ręcznie załadować zestaw personalizacji. Nie było automatycznego mechanizmu określania pewnego zestawu personalizacji, który powinien być dostępny dla użytkownika w danej roli.

Przy użyciu funkcji zapisanych widoków zarządzanie organizacyjne personalizacjami jest znacznie łatwiejsze, głównie ze względu na możliwość publikowania widoków w rolach zabezpieczeń. Gdy widok zostanie opublikowany, każdy użytkownik mający taką rolę będzie mógł uzyskać dostęp do tego widoku i korzystać z niego, niezależnie od dostępności funkcji personalizacji dla użytkownika. Chociaż każdy użytkownik ma kopię opublikowanego widoku, do której jest stosowane użycie strony (jawne personalizacje), żaden użytkownik nie może zapisać jawnych personalizacji lub aktualizacji kwerendy w opublikowanym widoku (co oznacza, że opublikowane widoki są zablokowane). Ponadto, jeśli nowi użytkownicy otrzymają rolę, w której widok został opublikowany, będą automatycznie widzieć widoki skojarzone z ich rolami bez żadnych działań administratora. Podobnie, jeśli użytkownik zmieni role w organizacji, widoki skojarzone z jego poprzednią rolą nie będą już dla niego dostępne bez konieczności wykonania żadnych działań przez administratora. Aktualizacje opublikowanego widoku mogą być łatwo dystrybuowane użytkownikom przez ponowne opublikowanie widoku do odpowiednich ról zabezpieczeń.

Możliwość publikowania umożliwia organizacjom definiowanie standardowych widoków firmowych zoptymalizowanych pod kątem ich działalności skierowanych do użytkowników mających określone role zabezpieczeń.  

## <a name="publishing-views"></a>Publikowanie widoków
Podczas procesu publikowania można przypisać widoki do roli lub ról zabezpieczeń, co oznacza, że każdy użytkownik dysponujący tą rolą będzie mógł uzyskać dostęp do tego widoku i korzystać z niego, ale nie będzie mógł go edytować. Obecnie tylko administratorzy systemu mają prawa do akcji **Publikuj** w menu rozwijanym selektor widoku, ale nowa rola zabezpieczeń będzie dostępna w przyszłej aktualizacji, aby nadać prawa publikowania innym zaufanym użytkownikom.  

Aby opublikować widok, należy wykonać następujące kroki: 
1.  Utwórz i zapisz osobistą kopię widoku, który chcesz opublikować. 
2.  Po załadowaniu tego widoku wybierz nazwę widoku, aby otworzyć menu rozwijane selektora widoków. 
3.  Naciśnij przycisk **Więcej**, a następnie wybierz opcję **Publikuj**. Zostanie otwarte okno dialogowe Publikowanie.  
4.  Podaj nazwę i (opcjonalnie) opis widoku. Jest to nazwa, którą użytkownicy otrzymujący ten widok będą widzieć w selektorach widoku. Nazwy publikowanych widoków nie mogą się powtarzać na stronie, nawet jeśli są stosowane do różnych list ról.  
5.  Dodaj role zabezpieczeń odpowiadające użytkownikom, którzy otrzymają ten widok.  
6.  Wybierz opcję **Publikuj**.

W niektórych środowiskach może upłynąć trochę czasu (do godziny), zanim użytkownicy zobaczą opublikowany widok.

## <a name="modifying-a-published-view"></a>Modyfikowanie opublikowanego widoku
Po opublikowaniu widoku może się okazać, że użytkownik chce wprowadzić zmiany w opublikowanym widoku. Chociaż nie można wprowadzać zmian w samych opublikowanych widokach, ponieważ są one zablokowane dla wszystkich użytkowników (w tym tych, którzy je opublikowali), to można ponownie opublikować widok, aby dokonać jego aktualizacji.  

Jeśli zmiany, które mają zostać wprowadzone do opublikowanego widoku, obejmują tylko parametry publikowania (nazwa i opis widoku lub role zabezpieczeń, dla których jest publikowany widok), należy wykonać następujące czynności: 
1.  Przełącz się na opublikowany widok z parametrami, które chcesz zaktualizować. 
2.  Wybierz opcję **Publikuj** z menu rozwijanego selektora widoku. 
3.  Wybierz opcję **Tak**, jeśli chcesz zaktualizować istniejący widok (lub **Nie**, jeśli chcesz go opublikować pod inną nazwą).
4.  Zaktualizuj nazwę, opis i/lub role zabezpieczeń tego widoku. 
5.  Wybierz opcję **Publikuj**. 
6.  Jeśli zaktualizowano nazwę opublikowanego widoku, należy również usunąć opublikowany widok ze starą nazwą (więcej informacji znajduje się w sekcji **Zarządzanie opublikowanymi widokami**). 

Jeśli zmiany w publikowanym widoku obejmują modyfikację personalizacji lub filtrów skojarzonych z widokiem, należy wykonać następujące czynności: 
1.  Przełącz się na opublikowany widok, który chcesz zmodyfikować. 
2.  Zapisz kopię opublikowanego widoku, aby utworzyć lokalną wersję roboczą opublikowanego widoku. 
3.  Zmodyfikuj lokalną wersję roboczą zgodnie z wymaganiami.
4.  Opublikuj widok pod pierwotną nazwą. 

## <a name="managing-published-views"></a>Zarządzanie opublikowanymi widokami
Podobnie jak w przypadku zarządzania widokami osobistymi okno dialogowe **Zarządzaj moimi widokami** oferuje użytkownikom z uprawnieniami do publikowania podstawowe możliwości kontroli nad opublikowanymi widokami tej strony (oprócz ich widoków osobistych). Jeśli chcesz otworzyć tę stronę, wybierz nazwę widoku, aby otworzyć menu rozwijane selektora widoków, wybierz opcję **Więcej**, a następnie wybierz opcję **Zarządzaj moimi widokami**.

O ile karta **Moje widoki** z listą widoków osobistych jest widoczna dla wszystkich użytkowników, to karta **Opublikowane** z listą wszystkich opublikowanych widoków danej strony jest wyświetlana tylko użytkownikom z uprawnieniami do publikowania. Ponieważ widoki mogą być publikowane przez różnych użytkowników, ważne jest, aby każdy mógł zarządzać pełną listą opublikowanych widoków, niezależnie od tego, czy dany użytkownik faktycznie opublikował widok.

Dostępny zestaw akcji dla listy wszystkich opublikowanych widoków strony jest następujący. 

-    **Publikuj**: akcja **Publikuj** umożliwia ponowne opublikowanie widoku ze zmodyfikowanymi parametrami publikowania (nazwa, opis, role zabezpieczeń).  
-    **Usuń**: akcja **Usuń** umożliwia trwałe usunięcie opublikowanego widoku. Ta akcja powoduje usunięcie widoku dla wszystkich użytkowników w systemie.  
 
Zmiany wprowadzone w tym oknie dialogowym zaczną obowiązywać, gdy zostanie naciśnięty przycisk **Zapisz**.

## <a name="frequently-asked-questions"></a>Często zadawane pytania
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Jak włączyć zapisane widoki w środowisku? 
Aby włączyć zapisane widoki, gdy funkcja jest w podglądzie, wykonaj następujące czynności: 

1.  **Włącz funkcję testową**: wykonaj następującą instrukcję SQL: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLISavedViewsEnableFeature', 1, 0, 5637144576);`

2. **Zresetuj usługi IIS**, aby opróżnić statyczną dystrybucję testową pamięci podręcznej. 

3.  **Znajdź funkcję**: przejdź do obszaru roboczego **Zarządzanie funkcjami**. Jeśli **Zapisane widoki** nie są wyświetlane na liście, wybierz przycisk **Sprawdź aktualizacje**.   

4.  **Włącz funkcję**: Znajdź funkcję **Zapisane widoki** na liście funkcji i wybierz przycisk **Włącz teraz** w okienku szczegółów.

Wszystkie kolejne sesje użytkownika będą uruchamiane z włączonymi zapisanymi widokami.  

Jeśli personalizacja jest wyłączona dla środowiska, widoki zostaną wyłączone nawet po wykonaniu powyższych kroków. Jest to spowodowane tym, że funkcja widoków jest nałożona na podsystem personalizacji.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Co się dzieje z istniejącymi personalizacjami, gdy są włączone widoki? 
Po włączeniu widoków wszelkie istniejące personalizacje użytkownika i formularza są zapisywane w nowym widoku o nazwie **Mój widok**, który jest automatycznie ustawiany jako widok domyślny. Ma to na celu zapewnienie spójnego środowiska użytkownika przed włączeniem widoków i po nim, z wyjątkiem formantu selektora widoków wyświetlanego w formularzach.  

### <a name="what-pages-support-views"></a>Jakie strony obsługują widoki? 
Widoki są dostępne dla większości, ale nie wszystkich stron w module Finance and Operations. Dokładnie rzecz biorąc, widoki są obecnie dostępne na wszystkich stronach pełnoekranowych, z wyjątkiem pulpitów nawigacyjnych i obszarów roboczych. Strony niepełnoekranowe, zawierające okna dialogowe, okna dialogowe rozwijane, wyszukiwania, rozszerzone podglądy, również obecnie nie obsługują widoków. Obsługa widoków na dodatkowych stronach, jak obszary robocze i okna dialogowe, być może zostanie dodana w przyszłej aktualizacji.   

### <a name="who-is-allowed-to-publish-views"></a>Kto ma prawo do publikowania widoków?
Obecnie jedynymi użytkownikami, którzy mają uprawnienia do publikowania widoków, są administratorzy systemu.  W przyszłej aktualizacji planowana jest nowa rola zabezpieczeń, która pozwoli klientom z większą elastycznością decydować, kto może publikować.  

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Dlaczego nie można zapisać filtrów w widoku? 
Istnieje kilka przyczyn uniemożliwiających zapisanie filtru w widoku: 

- Strona może nie obsługiwać zapisywania filtrów w ramach definicji widoku. Tylko strony z dużymi selektorami widoku umożliwiają zapisywanie personalizacji i modyfikacji kwerend w postaci widoku. Więcej informacji znajduje się w sekcji „Przełączanie widoków”. 

- Jeśli widok jest widokiem domyślnym, a ścieżka nawigacji do strony zawiera kwerendę, kwerenda widoku początkowo może nie zostać zastosowana. Oto dwa podstawowe scenariusze takiej sytuacji: 
     - Jeśli przejdziesz do strony z kafelka, kwerenda kafelka zostanie wykonana niezależnie od kwerendy skojarzonej z domyślnym widokiem. 
     - Jeśli przejdziesz do strony i ten punkt wejścia zawiera kwerendę, pierwotna kwerenda będzie początkowo wykonywana zamiast kwerendy domyślnego widoku. 
     
  O wystąpieniu takiej sytuacji powinien ostrzegać komunikat informacyjny wyświetlany podczas ładowania widoku. Można to również potwierdzić, przełączając się do tego widoku po załadowaniu strony, ponieważ wtedy kwerenda widoku powinna zostać bezwzględnie wykonana.  

- Ta strona może nie obsługiwać poprawnie widoków, ponieważ może całkowicie zignorować kwerendę widoku lub może działać na tymczasowej tabeli, której dane nie są trwałe. 
