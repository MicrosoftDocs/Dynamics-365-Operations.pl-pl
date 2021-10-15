---
title: Omówienie procesu produkcji
description: Ten temat zawiera omówienie procesów produkcji. Opisuje różne etapy zleceń produkcyjnych, szarż produkcji i zadań Kanban — od utworzenia zamówienia aż do zamknięcia okresu finansowego.
author: johanhoffmann
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, Kanban, ProdTable, ProdTableOverview, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, OpResLifecycleManagementWorkspace, ProdParmCostEstimation, ProdParmRelease, ProdSchedule, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19832"
- intro-internal
ms.assetid: 0e83c7ea-feba-4ed6-8717-8b48a3b8804a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43530dceefa264755114d9a0e81c19682b1af20c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574528"
---
# <a name="production-process-overview"></a>Omówienie procesu produkcji

[!include [banner](../includes/banner.md)]

Ten temat zawiera omówienie procesów produkcji. Opisuje różne etapy zleceń produkcyjnych, szarż produkcji i zadań Kanban — od utworzenia zamówienia aż do zamknięcia okresu finansowego. 

Produkcja towarów, nazywana też cyklem produkcyjnym, następuje zgodnie z określonymi krokami potrzebnymi do ukończenia produkcji towaru. Cykl życia rozpoczyna się od utworzenia zlecenia produkcyjnego, zamówienia partii lub kanban. Kończy się, gdy wyprodukowany towar jest gotowy do dostarczenia odbiorcy lub przekazania do kolejnej fazy produkcji. Na każdym etapie cyklu produkcyjnego do jego ukończenia są potrzebne inne rodzaje informacji. Gdy etap zostaje ukończony, jest to odzwierciedlane w zleceniu produkcyjnym, zamówieniu partii lub kanban przez zmianę jego stanu produkcji. Różne rodzaje produktów wymagają różnych procesów produkcji.  

Moduł **Kontrola produkcji** jest połączony z innymi modułami, takimi jak **Zarządzanie informacjami o produktach**, **Zarządzanie zapasami**, **Księga główna**, **Zarządzanie magazynem**, **Księgowość projektu** i **Administrowanie organizacją**. Taka integracja sprzyja przepływowi informacji, który jest wymagany do ukończenia produkcji towaru.  

Na proces produkcji mają z reguły wpływ metody rachunku kosztów i inwentaryzacji zapasów, wybrane dla określonego procesu produkcyjnego. Supply Chain Management obsługuje zarówno metody kosztu rzeczywistego (\[FIFO\]; pierwsze na wejściu, pierwsze na wyjściu \[LIFO\]; średnia ruchoma i okresowa średnia ważona), jak i kosztu standardowego. Lean manufacturing wdraża się na podstawie reguły wyceny wstecznej.  

Wybór metod pomiaru kosztów określa również wymagania dotyczące raportów na temat zużycia zasobów i materiałów w procesie produkcji. Zazwyczaj metody kosztu rzeczywistego wymagają dokładnej sprawozdawczości na poziomie zadania, a metody kosztów okresowych pozwalają na mniej szczegółowe raportowanie zużycia materiałów i zasobów.

## <a name="mixed-mode-manufacturing"></a>Tryb mieszany produkcji
Różne produkty i topologie produkcji wymagają stosowania różnych typów zamówienia. Supply Chain Management może połączyć różne typy zamówienia w tryb mieszany. Innymi słowy wszystkich w całym cyklu produkcji gotowego towaru mogą wystąpić wszystkie typy zamówień.

-   **Zlecenie produkcyjne** — jest to typ klasycznego zlecenia produkcji do wyprodukowania określonego produktu lub wariantu produktu w określonej ilości w danym dniu. Zlecenia produkcyjne są oparte na specyfikacji listy składowej BOM i marszruty.
-   **Zamówienie partii** — ten typ zamówienia jest używany w produkcji procesowej i dyskretnej, gdzie konwersja produkcji opiera się na formule lub produkty towarzyszące i uboczne mogą być produktami końcowymi zamiast lub oprócz produktu głównego. Zamówienia partii wykorzystują BOM i marszruty typu **formuły**.
-   **Kanban** — karty Kanban są używane do sygnalizowania powtarzających się procesów lean manufacturing, opartych na przepływach produkcji, regułach kanban i BOM.
-   **Projekt** — projekt produkcji łączy produkty i usługi o określonym harmonogramie i budżecie. Część produkcyjna projektu może być zrealizowana poprzez dowolny inny typ zlecenia.

## <a name="manufacturing-principles"></a>Zasady produkcji
Aby wybrać zasady produkcji najlepiej dostosowane do określonego produktu i rynku, należy rozważyć wymagania dotyczące produkcji i logistyki oraz oczekiwania odbiorców dotyczące czasu realizacji dostawy.

-   **Produkcja na magazyn** — to klasyczna zasada produkcji, gdzie produkty są wytwarzane jako zapasy na podstawie prognozy lub minimalnego uzupełnienia zapasów (te ostatnie są zazwyczaj obliczane w oparciu na prognozie lub zużyciu historycznym).
-   **Produkcja na zamówienie** — standardowe produkty są produkowane na zamówienie lub gotowe do zamówienia. Mimo że produkcja wstępna może zostać zrealizowana przy użyciu reguły Produkcja na magazyn, kosztowne etapy łańcucha wartości lub etapy tworzące warianty, są uruchamiane przez zamówienie sprzedaży lub zamówienie przeniesienia.
-   **Konfigurowanie do zamówienia** — jak dla zasady Produkcja na zamówienie, ostateczne operacje łańcucha wartości są wykonywane na zamówienie. Rzeczywisty produkowany wariant produktu nie jest wstępnie zdefiniowany, tylko jest tworzony w chwili wprowadzania zamówień na podstawie modelu konfiguracji produktu sprzedaży. Reguła Konfigurowanie do zamówienia wymaga określonego poziomu unifikacji procesu dla danej linii produktów.
-   **Projektowanie na zamówienie** — te procesy są zazwyczaj wskazywane w projekcie i zaczynają się od fazy projektowania. Podczas fazy projektowania tworzy się koncepcje i opis produktów koniecznych do realizacji zamówienia. Następnie można utworzyć zlecenia produkcyjne, zamówienia partii lub kanban do wyprodukowania produktów.

## <a name="overview-of-the-production-life-cycle"></a>Omówienie cyklu produkcyjnego
Dla wszystkich typów trybu mieszanego produkcji mogą wystąpić następujące kroki w cyklu produkcyjnym. Jednak nie wszystkie z nich są przedstawiane jako stan zlecenia jawny.

1.  **Utworzone** — można tworzyć zlecenia produkcyjne, zamówienia partii lub kanban ręcznie, ale można też skonfigurować ich tworzenie przez system na podstawie różnych sygnałów popytu. Planowanie główne tworzy zlecenia produkcyjne, zamówienia partii, lub karty Kanban przy ustalaniu zamówień planowanych. Innymi sygnałami popytu są zamówienia sprzedaży lub sygnały ustalonej dostawy ze zleceń produkcyjnych lub kart kanban. W przypadku kart kanban o stałej ilości sygnały popytu są generowane, gdy kanban zostaną zarejestrowane jako puste.
2.  **Szacowane**— Umożliwia obliczanie oszacowań zużycia materiałów i zasobów. Oszacowanie generuje transakcje magazynowe dla surowców, które znajdują się w stanie **Zamówione**. Przyjęcia dla głównych produktów, produktów towarzyszących i ubocznych są generowane po oszacowaniu zleceń produkcyjnych lub zamówień partii. Jeśli lista składowa BOM zawiera wiersze typu **Ustalona dostawa**, zamówienia zakupu materiałów lub usług operacyjnych podwykonawcy są generowane i ustalane w zleceniu produkcyjnym lub szarży produkcyjnej. Towary lub zamówienia są rezerwowane zgodnie ze strategią rezerwacji zlecenia produkcyjnego, a cena towarów gotowych jest obliczana na podstawie ustawień parametrów.
3.  **Zaplanowane** — można zaplanować produkcję na podstawie operacji, pojedynczych zadań lub jednych i drugich.
    -   **Planowanie operacji** — ta metoda planowania zapewnia ogólny, długoterminowy plan. Za pomocą tej metody można przypisywać do zleceń produkcyjnych daty początkowe i końcowe. Jeśli zlecenia produkcyjne są dołączone do operacji marszruty, można je przypisać do grup centrów kosztów.
    -   **Planowanie zadań** — ta metoda planowania zapewnia plan szczegółowy. Każda operacja jest rozbita na pojedyncze zadania z określonymi datami i godzinami oraz przypisanymi zasobami operacyjnymi. W przypadku uwzględniania ograniczonych zadania są przypisywane do zasobów operacyjnych według ich dostępności. Harmonogram można przeglądać i zmieniać na wykresie Gantta.
    -   **Harmonogram Kanban** — zadania Kanban są planowane na tablicy harmonogramu kanban lub automatycznie planowane na podstawie automatycznego planowania konfiguracji reguł kanban.

4.  **Zwolnione** — można zwolnić zlecenie produkcyjne lub zamówienie partii, jeśli harmonogram został ukończony, a materiał jest dostępny do pobrania lub przygotowania. Sprawdzanie dostępności materiałów pomaga kierownikowi produkcji ocenić dostępność materiału dla zlecenia produkcyjnego lub zamówienia partii. Można również wydrukować dokumenty związane ze zleceniem produkcyjnym, takie jak listy pobrania, karta zadania, karta marszruty i zadanie marszruty. Wraz z wystawieniem zlecenia produkcyjnego stan zlecenia ulega zmianie, wskazując, że produkcja może się rozpocząć. W przypadku zarządzania magazynem, zwalnianie zlecenia produkcyjnego lub zamówienia partii powoduje zwolnienie wierszy BOM produkcji do zarządzania magazynem. Grupy czynności magazynowych i praca magazynowa są generowane na podstawie konfiguracji magazynu.
5.  **Przygotowane**/**Pobrane** — Po przygotowaniu wszystkich materiałów i zasobów w miejscu produkcji następuje aktualizacja wierszy BOM produkcji lub wierszy Kanban do stanu **Pobrane**. Zamówienia z ustaloną dostawą i związana z tym praca magazynu są zazwyczaj kończone na tym etapie. Karty kanban lub karty zadań wymagane do zgłaszania postępów produkcji powinny zostać przypisane i wydrukowane.
6.  **Rozpoczęte** — po uruchomieniu zlecenia produkcyjnego, zamówienia partii lub kanban można zgłosić wykorzystanie materiałów lub zasobów w związku z zamówieniem. System można skonfigurować tak, aby automatycznie księgował zużycie materiałów i zasobów, które są alokowane do zamówienia po uruchomieniu zlecenia. Przydział ten jest znany jako „wstępna kalkulacja zużycia”, „rozliczenie wstępne” lub „samozużycie”. Można ręcznie alokować materiały dla zleceń produkcyjnych lub zamówień partii, tworząc dodatkowe arkusze list pobrania. Do zamówienia można także ręcznie przydzielić robociznę oraz inne koszty marszruty. Jeśli używasz planowania operacji, możesz alokować te koszty przez utworzenie arkusza karty marszruty. Jeśli używasz planowania zadań, możesz alokować te koszty przez utworzenie arkusza karty zadania. Zlecenia produkcyjne lub zamówienia partii można uruchomić w partiach żądanej ilości końcowej. W ramach zlecenia produkcyjnego, zamówienia partii lub kanban tworzone są zadania, które można rozpoczynać i zgłaszać osobno przy użyciu arkuszy, terminalu MES lub tablic kanban.
7.  Zgłaszanie postępu/**zakończenia** zadania — za pomocą terminalu MES, arkuszy produkcji, tablic kanban lub funkcji skanowania mobilnego można zgłaszać postęp produkcji według zadania lub zasobu. Zużycie materiałów i zasobów zostanie zaksięgowane, a stan powiązanych kanban, zleceń produkcyjnych i zamówień partii może zostać zaktualizowany do wartości **otrzymane** lub **zgłoszone jako gotowe**. W zależności od konfiguracji magazynu można utworzyć pracę odłożenia.
8.  **Zgłoszone jako gotowe** (przyjęcie produktów) — Gdy zlecenie produkcyjne lub zamówienie partii zostanie zgłoszone jako zakończone, ilość wyprodukowanych towarów, które zostały zakończone, jest aktualizowana w module Zapasy. Ilość ta zawiera ilość odpowiednich produktów towarzyszących i ubocznych. Jeśli używasz księgowania pracy w toku (PWT), w arkuszu księgi następuje zmniejszenie kont PWT i zwiększenie zapasów produktów gotowych. Podczas obliczania kosztów zlecenia produkcyjnego księgowany jest rzeczywisty koszt produkcji. Jeśli koszty materiałów i robocizny, które są powiązane z produkcją nie są już przydzielone do arkusza lub przez wstępną kalkulację zużycia, mogą one być automatycznie przydzielane przez rozliczenie wsteczne. Alokacja poprzez opróżnianie zaległe uwzględnia rozliczenie wsteczne procesów transakcji magazynowych. Jeśli zlecenie produkcyjne zostało zakończone, należy wybrać pole wyboru **Zakończ zadanie**, aby zmienić pozostały stan na **Zakończone**. W przeciwnym razie to pole jest pozostawiane puste w celu informowania o dodatkowych ilościach, które są produkowane.
9.  **Ocena jakości** — dokument przyjęcia produktów może spowodować utworzenie zlecenia kontroli jakości, w zależności od konfiguracji procesów testowych i reguł kontroli jakości, które są ustalone dla poszczególnych produktów. Ze względu na to, że zlecenie kontroli jakości może powodować aktualizowanie stanu zapasów lub atrybutów partii testowanych produktów, ocena jakości jest obowiązkowym procesem w wielu branżach.
10. **Odkładanie** i **wysłanie zamówienia** — po przyjęciu produktów i ocenie jakości opcjonalna praca odłożenia kieruje otrzymane produkty do następnego punktu zużycia, do magazynu produktów gotowych lub do strefy wysyłki, jeśli jest takie wymaganie.
11. **Zakończone** — Przed zakończeniem produkcji obliczane są rzeczywiste koszty dla wyprodukowanej ilości. Wszystkie szacowane koszty materiałów, robocizny i narzutów zostają wycofane i zastąpione kosztami rzeczywistymi. Jeśli w momencie uruchamiania obliczenia kosztów jest zaznaczone pole wyboru **Zakończ zadanie**, stan zlecenia produkcyjnego zmienia się na **Zakończone**. Ten stan zapobiega zaksięgowaniu dodatkowych kosztów dla ukończonego zlecenia produkcyjnego.
12. **Zamknięcie okresu** — niektóre zasady rachunku kosztów, takie jak średnia okresowa, wycena wsteczna, FIFO lub LIFO wymagają okresowych działań w celu zamknięcia zapasów lub okresu obrachunkowego. Na ogół system próbuje zgłosić całe zużycie materiałów i zasobów oraz korekty zapasów i odpadków przed zamknięciem okresów. Zgłoszenie to odbywa się zwykle za pomocą arkuszy przesunięć magazynowych lub arkuszy korekt. Celem jest dokonanie oceny wyników ekonomicznych jednostek operacyjnych na okres. W niektórych przypadkach, gdy używane są zlecenia produkcyjne obejmujące okresy raportowania finansowego, stosuje się arkusze produkcyjne do zgłaszania postępów produkcji i zużycia zasobów na koniec okresu.


## <a name="additional-resources"></a>Dodatkowe zasoby

[Informacja zwrotna o produkcji](production-feedback.md)

[Omówienie modeli konfiguracji produktu](../pim/product-configuration-models.md)

[Omówienie wytwarzania typu lean manufacturing](lean-manufacturing-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]