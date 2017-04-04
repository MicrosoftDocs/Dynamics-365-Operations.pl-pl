---
title: "Zarządzanie prac podwykonawczych w produkcji"
description: "W tym temacie wyjaśniono jak podwykonawców operacje są zarządzane w Microsoft Dynamics 365 dla operacji. Innymi słowy wyjaśnia, jak działalności produkcyjnej, które są przydzielone do zasobu są zarządzane przez dostawcę."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 79430358bebd93fd96f1169d22737d3537dbfc08
ms.lasthandoff: 03/31/2017


---

# <a name="manage-subcontracting-work-in-production"></a>Zarządzanie prac podwykonawczych w produkcji

W tym temacie wyjaśniono jak podwykonawców operacje są zarządzane w Microsoft Dynamics 365 dla operacji. Innymi słowy wyjaśnia, jak działalności produkcyjnej, które są przydzielone do zasobu są zarządzane przez dostawcę.

W [procesów produkcji](production-process-overview.md), można wykonać przez zasoby, które są własnością lub administrowanych przez dostawców. Zasoby dostawcy są zazwyczaj używane do poziomu okresowe nadmierny popyt, która przewyższa dostępnych zdolności produkcyjnych firmy środków własnych. Dostawca może również być w stanie zaoferować szczególne [możliwości zasobów](resource-capabilities.md)lub zasobów po niższej cenie.  

W zależności od zasobów dostawcy, które są używane w procesie produkcyjnym [trasa](routes-operations.md) często ma dodatkowe wymagania logistyczne, ponieważ materiały i półprodukty najpierw muszą być transportowane do witryny dostawcy. Następnie wynik operacji podwykonawcy muszą być przewożone do lokalizacji, która jest przydzielona do następnej operacji lub do składu gotowego towaru.  

Gdy używane są podzlecenia operacji lub działalności, wpływają one na wszystkich etapach działań z definicji operacji, które są wymagane w produkcji, wyceny, prognozowania, planowania i planowania, zarządzania logistycznego dla materiałów, półproduktów i wyrobów gotowych. Wreszcie tych zasobów wymaga ich własnych procesach dla kontroli księgowości i kosztów.  

Dla zasobów wewnętrznych stawka kosztu stałego zazwyczaj jest przydzielany przez okres. Z drugiej strony Koszt podwykonawców zasobów opiera się na cenę nabycia związaną z nimi pracę. Usługa jest zdefiniowany jako inny produkt i jest używany do jazdy zamówień i zakupów procesów dla danej operacji podwykonawcy.  

Obecnie nie ma pojęcia jawne półproduktów w usłudze Microsoft Dynamics 365 dla operacji. Dla zlecenia produkcyjnego, który wymaga więcej niż jednej operacji w celu przekształcenia surowców do wyrobu gotowego wyrobu gotowego jest księgowana do zapasów tylko w ostatniej operacji. Półprodukty powodującymi wcześniejszych operacji księguje się w pracy w toku (PWT), ale nie są zaksięgowane lub śledzone w magazynie. Choć trasy i zestawień komponentów (BOM-ów) można podzielić na wiele mniejszych jednostek, podejście to zwiększa się liczba produktów, BOM-ów i marszrut, które muszą być zarządzane.  

Istnieją dwie metody modelowania, podwykonawstwo prac do działalności produkcyjnej. Metody te różnią się w taki sposób, że proces podwykonawstwa mogą być modelowane, sposób, aby półprodukty są reprezentowane w procesie i sposób, w jaki Kontrola kosztów jest zarządzany.

-   Zlecanie operacji marszruty zlecenia produkcyjnego lub szarże produkcyjne
    -   Usługi produktu musi być zaopatrzony produktu i musi być częścią danego zestawienia komponentów.
    -   Ta metoda obsługuje FIFO, po raz pierwszy (FIFO) lub koszt standardowy.
    -   Półprodukty są reprezentowane przez usługi produktu w procesie.
    -   Kontrola kosztów przydziela koszty, które są skojarzone z pracy podwykonawcy do kosztów materiałów.
-   Zlecanie działań przepływu produkcji w przepływie produkcji oszczędnej
    -   Usługa jest produktem usługi nienależącego do zapasów, a nie jest częścią danego zestawienia komponentów.
    -   Metoda ta wykorzystuje umów zakupu jako umów serwisowych.
    -   Metoda ta wykorzystuje wyceny wstecznej.
    -   Ta metoda umożliwia zamówień zbiorczych i asynchroniczne. (Przepływ materiału jest niezależny od procesu zamówień).
    -   Kontrola kosztów przydziela prac podwykonawczych w swoim własnym bloku podział kosztów.

## <a name="subcontracting-of-route-operations"></a>Zlecanie operacji marszruty
Aby użyć zlecanie operacji marszruty dla produkcji lub szarże produkcyjne, usługi produktu, który jest używany dla zamówień na usługi musi być zdefiniowana jako produkt **Service** typu. Ponadto musi mieć grupę modeli towaru, który ma **Produkt magazynowany** opcję w obszarze **magazynu zasad** ustawioną **tak**. Opcja ta określa, czy produkt jest księgowane jako zapasy w dokumencie przyjęcia produktów (**Produkt magazynowany** = **tak**), lub czy produkt jest ujmowane w rachunku zysków i strat (**Produkt magazynowany** = **nr**). Chociaż to zachowanie może wydawać się sprzeczne, to opiera się na fakcie, że tylko produkty, które mają te zasady spowoduje utworzenie transakcji magazynowych, które mogą być używane w kontroli kosztów Aby obliczyć koszt planowany i określić rzeczywisty koszt po zakończeniu zlecenia produkcyjnego.  

Należy uznać w obliczeniach planowania i kosztów, należy dodać usługę do BOM. Wiersz BOM musi być **dostawcy** typu, a muszą być przydzielone do którego usługa zostanie przydzielona do operacji marszruty. Ta operacja marszruty musi mieć zasób wyceny i zapotrzebowanie na zasoby odsyłających do zasobów z **dostawcy** typu, który łączy operacji i związaną z nimi pracę na odpowiednim koncie dostawcy.  

Gdy używana jest ta konfiguracja, zamówienie zakupu jest tworzone dla produktu związaną z nimi pracę, w oparciu o oszacowania zlecenia produkcyjnego. Zamówienie zakupu usługi jest używany jako kotwica dla operacji podwykonawcy. Prac podwykonawczych można zarządzać za pomocą **Praca zlecona** strony listy w kontroli produkcji. Prac podwykonawczych służy do wysłania do dostawcy, w ramach przygotowań do operacji surowca, a ostatecznie półprodukt. Również służy do odbierania uzyskane produkty zamówione operacji w przyjęcia towaru, gdzie usługi produktu służy do identyfikacji przybycia produktu do półproduktów. Jeśli wiersza zamówienia zakupu zostanie odebrany, operacji produkcji jest aktualizowana jako ukończone.  

Zlecenie produkcyjne może mieć wiele operacji, a każda operacja mogą być przydzielone do innego dostawcy. W związku z tym zlecenia produkcyjnego end-to-end może wywołać wielu zamówień zakupu.

## <a name="subcontracting-of-production-flow-activities"></a>Zlecanie działań przepływu produkcji
[Produkcji oszczędnej](lean-manufacturing-overview.md)rozwiązanie modele prac podwykonawczych jako usługa, która jest powiązane z działaniem, z [przepływ produkcji](http://ax.help.dynamics.com/en/wiki/create-a-production-flow-version/) (temat dotyczący zadania). W związku z tym, podwykonawstwo tego typu jest również zwany [według działalności podwykonawstwa.](activity-based-subcontracting.md) Specjalny typ grupy kosztów **outsourcingu bezpośredniego**, została wprowadzona, i usług podwykonawczych nie są częścią BOM produktów gotowych. Korzystając z produkcji oszczędnej, wszystkie czynności są definiowane przez kart Kanban, które mogą być związane z jednego lub wielu działań przepływu produkcji. Tak daleko to wyjaśnienie brzmi jak wyjaśnienie zleceń produkcyjnych. Jednakże konieczne zleceń produkcyjnych zawsze musi kończyć się produktu gotowego, można utworzyć karty Kanban do dostarczania półprodukt. Nie masz do wprowadzenia nowego produktu i poziomu BOM.  

Ponieważ reguły kanban może być bardzo dynamiczny, można modelować różne warianty dostaw dla tego samego produktu w przepływie produkcji. Korzystając z produkcji oszczędnej podwykonawstwo, przepływu materiałów i przepływów finansowych są ściśle oddzielone. Wszystkie przepływu materiału jest reprezentowana przez działalność kanban. Zamówienia zakupu dla produktów usług i księgowanie przyjęcia tych usług można zautomatyzować, na podstawie stanu zadań w systemie kanban w procesie produkcji. Zadań w systemie Kanban może być uruchomione i zakończone, zanim jeszcze zamówienia zakupu są tworzone. Dokumenty podwykonawstwa (zamówienia zakupu i przyjęcie zakupu usługi) może być agregowane przez okres i usługi. W związku z tym liczba dokumentów zakupu i wierszy można przechowywać małe, nawet w operacjach zawierających dużą liczbę powtórzeń, gdzie producenci oferują usług podwykonawczych w przepływ Jednoelementowy.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modelowanie podwykonawstwa w przepływie produkcji

W [chudego przepływu produkcji](lean-manufacturing-modeling-lean-organization.md), działania procesu może być zdefiniowany jako zlecona, gdy jest ona przeznaczona dla komórki roboczej (grupę zasobów), który ma zasób jednego dostawcy. Gdy komórka robocza podwykonawcom, działań związanym z procesem muszą być połączone do wiersza umowy zakupu aktywne, zawierającego przedmiot serwisu i cenę usługi. Umowy serwisowej działania definiuje również obliczenia stosunek między ilością produktu zadania w systemie kanban i wynikowe ilości usługi. Można wybrać, czy usługa jest ona obliczana na podstawie liczby miejsc pracy, ilość produktu dobry, raportowana w zadaniach lub ilość całkowita produktu (całkowita ilość obejmuje produkty wadliwe).  

Działania związane z transferem mogą być również definiowane jako wykonywane przez podwykonawców. Ta definicja niejawnie występuje po zaznaczeniu strony odpowiedzialnej za wysyłkę w działanie transferu. Po wybraniu **nadawcy** lub **odbiorcy**, jeśli odpowiednie źródło lub miejsce docelowe magazynu jest zarządzany przez dostawcę magazynu, działanie jest uważany za wykonywane przez podwykonawców. Po wybraniu **przewoźnika**, działanie jest zawsze wykonywane przez podwykonawców. Jak działania procesu podwykonawców, działanie transferu podwykonawców musi być podłączony do umowy serwisowej, w celu aktywowania przepływu produkcji.

### <a name="backflush-costing"></a>Wycena wsteczna

Rachunku kosztów prac podwykonawczych jest całkowicie zintegrowana wyceny dla produkcji oszczędnej roztwór (wyceny wstecznej). Po zaksięgowaniu przyjęcia zamówienia zakupu usługi lub po wystąpieniu fakturowania, koszt usługi jest przydzielany do przepływu produkcji. Dla wyceny wstecznej, odchylenie usług podwykonawczych obliczana jest przez potrącenie podwykonawstwa bloku cen ewidencyjnych otrzymanych produktów od ilości rzeczywiste usługi odebrane i zafakturowane.

## <a name="material-supply-for-subcontracted-operations"></a>Dostawy materiałów dla działań podwykonawczych
Półprodukty i inne związane z nimi materiały muszą zostać przeniesione do lokalizacji, gdzie fizycznie praca jest wykonywana. Użycie operacji podwykonawcy i działań, takie przeniesienie jest często związane z dodatkowych transportu do witryny obsługiwane przez dostawcę. Przydzielanie materiału w BOM do operacji podwykonawcy, zadeklarować, że materiał muszą być umieszczone w miejscu wejściowego grupy zasobów dla przydzielonego zasobu. Planowanie główne lub uzupełnienie produkcji oszczędnej następnie przepisy materiał do tej lokalizacji.  

Dla modelu magazynu, który znajduje się w witrynie dostawcy, jest najlepszym rozwiązaniem w przemyśle, aby zdefiniować zarządzane dostawcy magazynu. Można łatwo definiować magazynu dostawcy zarządzanych przez utworzenie nowego magazynu i przypisywanie konta dostawcy. Aby udokumentować tego materiału muszą zostać przeniesione do dostawcy zanim operacja może być wykonywana, należy przydzielić magazynu dostawcy zarządzanych do magazynu wejściowego grupy zasobów, która posiada zasobu.  

Aby uzupełnić materiał w tym magazynie, można użyć wiele strategii:

-   Zamówienia przeniesienia
-   Arkusze przeniesienia
-   Karty Kanban wypłat
-   Bezpośredniego nabycia do lokalizacji dostawcy

Półprodukty są wyjątkiem od tej reguły. Aby przetransferować półprodukty, użytkownik musi tylko te opcje:

-   Dla produkcji i szarże produkcyjne półprodukty mogą być transferowane tylko logicznie przy użyciu arkusza listy pobrania z **Praca zlecona** strony listy. Tego dziennika spowoduje utworzenie dokumentu dostawy, które mogą być używane do przenoszenia półproduktów i surowców do dostawcy.
-   Dla operacji podwykonawcy w przepływach produkcji transfer półprodukty jest udokumentowane przez daty otrzymania wycofania produkcji Kanban w lokalizacji dostawcy. Dla modelu działania transferu jawne, można zakończyć kanban produkcji do transferu dodatkowe działania.

**Uwaga:** marszruty produkcji dla zlecenia produkcyjnego pojedynczej nie może przekroczyć wielu witryn. Ta reguła dotyczy również prac podwykonawczych. W związku z tym magazyny reprezentujące zarządzanych dostawców zapisanych lokalizacji musi być zdefiniowana w tej samej lokacji co zasoby wewnętrzne, które są używane w marszrucie. Chociaż przepływów produkcji mogą przechodzić przez witryny, nie przewożą półprodukty z jednej witryny do innej, ponieważ ta operacja pociąga za sobą zmianę kontekstu kosztów.  

Zwykle Magazyn wyjściowy i lokalizacja grupy zasobów podwykonawców bezpośrednio są przydzielane do magazynu i lokalizacja następnego kroku działania w procesie produkcji lub marszruty. Ten Instalator pomaga zmniejszyć ilość zadanie raportowania, że występuje lub numer operacji transferu dodatkowe, które musi być modelowane.


