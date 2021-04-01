---
title: Zarządzanie pracą podwykonawczą w produkcji
description: W tym temacie opisano sposób zarządzania operacjami realizowanymi przez podwykonawców w Dynamics 365 Supply Chain Management. Innymi słowy przedstawiono, jak operacje produkcyjne przydzielone do zasobu są zarządzane przez dostawcę.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup, ProdBOMVendorListPagePreviewPane, ProdBOMVendor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66aed16cc3e2c3b33dfd40982d2211816c4e5047
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246004"
---
# <a name="manage-subcontracting-work-in-production"></a>Zarządzanie pracą podwykonawczą w produkcji

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób zarządzania operacjami realizowanymi przez podwykonawców w Dynamics 365 Supply Chain Management. Innymi słowy przedstawiono, jak operacje produkcyjne przydzielone do zasobu są zarządzane przez dostawcę.

W [procesach produkcji](production-process-overview.md) praca może być wykonywana przez zasoby, które należą lub są administrowane przez dostawców. Zazwyczaj zasoby dostawców są używane do zrównoważenia (zaspokojenia) okresowego nadmiernego popytu, który przewyższa dostępne zdolności produkcyjne własnych zasobów firmy. Dostawca może również być w stanie oferować określone [możliwości zasobów](resource-capabilities.md) lub zasoby w niższej cenie.  

W zależności od zasobów dostawcy wykorzystywanych w procesie produkcji [marszruta](routes-operations.md) często ma dodatkowe wymagania logistyczne, ponieważ materiały i półprodukty najpierw muszą zostać przetransportowane do lokacji dostawcy. Następnie rezultat operacji podwykonawczej musi zostać przetransportowany do lokalizacji przydzielonej dla następnej operacji lub do magazynu wyrobów gotowych.  

Gdy są używane operacje lub działania podwykonawcze, wpływają na wszystkie etapy operacji: od zdefiniowania operacji wymaganych w produkcji, przez wycenę, prognozowanie, planowanie i harmonogramowanie, aż po zarządzanie logistyką materiałów, półproduktów i wyrobów gotowych. Wreszcie te zasoby wymagają własnych procesów księgowości i kontroli kosztów.  

Dla zasobów wewnętrznych stawka kosztu stałego zazwyczaj jest przydzielana na okres. Z drugiej strony koszt zasobów podwykonawczych opiera się na cenie zakupu odnośnej usługi. Usługa jest definiowana jako osobny produkt i używana do realizacji procesów zaopatrzenia i zakupów w danej operacji podwykonawczej.  

Obecnie w usłudze Supply Chain Management nie ma osobnej encji półproduktów. W zleceniu produkcyjnym, które wymaga więcej niż jednej operacji w celu przekształcenia surowców na wyrób gotowy, wyrób gotowy jest księgowany z powrotem w zapasach dopiero w ostatniej operacji. Półprodukty powstające we wcześniejszych operacjach księguje się do pracy w toku (PWT), ale nie są one księgowane ani śledzone w zapasach. Choć marszruty i listy składowe (BOM) można podzielić na wiele mniejszych jednostek, takie podejście zwiększa liczbę produktów, list BOM i marszrut, którymi trzeba zarządzać.  

Istnieją dwie metody modelowania prac podwykonawczych (podwykonawstwa) w operacjach produkcyjnych. Metody te różnią się pod względem sposobu modelowania procesu podwykonawstwa, przedstawiania półproduktów w procesie i zarządzania kontrolą kosztów.

-   Podwykonawstwo operacji marszruty w zleceniach produkcyjnych lub szarżach produkcyjnych
    -   Produkt usługi musi być produktem magazynowanym i wchodzić w skład listy BOM.
    -   Ta metoda obsługuje format FIFO (pierwsze na wejściu, pierwsze na wyjściu) i koszt standardowy.
    -   Półprodukty są w procesie reprezentowane przez produkt usługi.
    -   Moduł Kontrola kosztów przydziela koszty skojarzone z pracą podwykonawczą do kosztów materiałów.
-   Podwykonawstwo działań przepływu produkcji w przepływie produkcji oszczędnej
    -   Usługa jest niemagazynowym produktem usługi i nie wchodzi w skład listy BOM.
    -   Ta metoda wykorzystuje umowy zakupu jako umowy o świadczenie usług (umowy serwisowe).
    -   Metoda wykorzystuje wycenę wsteczną.
    -   Ta metoda umożliwia stosowanie zaopatrzenia zagregowanego i asynchronicznego. (Przepływ materiału jest niezależny od procesu zaopatrzenia).
    -   Moduł Kontrola kosztów rozdziela pracę podwykonawczą w jej własnym bloku podziału kosztów.

## <a name="subcontracting-of-route-operations"></a>Podwykonawstwo operacji marszruty
Aby stosować podwykonawstwo operacji marszruty do zleceń produkcyjnych lub szarż produkcyjnych, produkt usługi używany dla zaopatrzenia w usługę musi być zdefiniowana jako produkt typu **Usługa**. Ponadto musi mieć grupę modeli pozycji, który ma opcję **Produkt magazynowany** w obszarze **Zasady zapasów** ustawioną na **Tak**. Ta opcja określa, czy produkt jest księgowany jako zapasy podczas przyjęcia produktów (**Produkt magazynowany** = **Tak**) czy też jest ujmowany w kosztach na koncie wynikowym (**Produkt magazynowany** = **Nie**). Chociaż to zachowanie może się wydawać sprzeczne, to opiera się na fakcie, że tylko produkty mające ustawioną tę zasadę będą tworzyły transakcje magazynowe, których można używać w kontroli kosztów do obliczania kosztu planowanego i określania kosztu rzeczywistego po zakończeniu zlecenia produkcyjnego.  

Aby usługa była uwzględniana w planowaniu i obliczeniach kosztów, musi być dodana do listy BOM. Wiersz BOM musi być typu **Dostawca** i być przydzielony do operacji marszruty, do której jest przydzielona usługa. Ta operacja marszruty musi mieć zasób wyceny oraz zapotrzebowanie na zasoby wskazujące zasób typu **Dostawca**, które łączy operację i odnośną usługę z odpowiednim kontem dostawcy.  

Gdy jest używana ta konfiguracja, jest tworzone zamówienie zakupu na odnośny produkt w oparciu o oszacowanie zlecenia produkcyjnego. Zamówienie zakupu na usługę jest używane jako zakotwiczenie dla operacji podwykonawczych. Pracą podwykonawczą można zarządzać za pomocą strony listy **Praca podwykonawcza** w module Kontrola produkcji. Praca podwykonawcza służy do wysłania dostawcy surowca i — ostatecznym rozrachunku — półproduktu w ramach przygotowań do operacji. Również służy do odbierania wynikowego produktu operacji podwykonawczej w sekcji przyjęcia towaru, gdzie produkt usługi służy do identyfikacji przybycia półproduktu. Po odebraniu towaru z wiersza zamówienia zakupu operacja produkcji jest aktualizowana jako ukończona.  

Zlecenie produkcyjne może mieć wiele operacji, a każda operacja może być przydzielona do innego dostawcy. W związku z tym całościowe zlecenie produkcyjne może inicjować wiele zamówień zakupu.

## <a name="subcontracting-of-production-flow-activities"></a>Podwykonawstwo działań przepływu produkcji
W rozwiązaniu [produkcji oszczędnej](lean-manufacturing-overview.md) praca podwykonawcza jest modelowana jako usługa powiązana z działaniem w [przepływie produkcji](tasks/create-production-flow-version.md) (temat przewodnika po zadaniu). W związku z tym ten rodzaj podwykonawstwa jest również zwany [podwykonawstwem działań.](activity-based-subcontracting.md) Wprowadzono specjalny typ grupy kosztów **Outsourcing bezpośredni**, a usługi podwykonawcze nie są częścią listy składowej (BOM) wyrobów gotowych. Podczas korzystania z produkcji oszczędnej wszystkie działania są definiowane przez karty Kanban, które mogą być powiązane z jednym lub wieloma działaniami przepływu produkcji. Na razie to wyjaśnienie brzmi jak wyjaśnienie koncepcji zleceń produkcyjnych. Jednak o ile zlecenia produkcyjne zawsze muszą się kończyć wyrobem gotowym, można utworzyć karty Kanban służące dostarczaniu półproduktów. Nie trzeba dodawać nowego produktu ani poziomu BOM.  

Ponieważ reguły Kanban mogą być bardzo dynamiczne, można modelować różne warianty dostarczania tego samego produktu w przepływie produkcji. Podczas korzystania z podwykonawstwa w produkcji oszczędnej przepływ materiałów jest ściśle oddzielony od przepływu finansowego. Cały przepływ materiałów jest reprezentowany przez działania Kanban. Zamówienia zakupu na produkty usług oraz księgowanie przyjęć tych usług można zautomatyzować na podstawie stanu zadań Kanban w przepływie produkcji. Zadania Kanban można uruchamiać i kończyć nawet przed utworzeniem zamówień zakupu. Dokumenty podwykonawstwa (zamówienia zakupu i dowody zakupu usług) mogą być agregowane według okresów i usług. Dzięki temu można zminimalizować liczbę dokumentów i wierszy zakupu, nawet dla operacji z dużą liczbą powtórzeń, gdzie dostawcy dostarczają usługi podwykonawcze w jednoelementowym przepływie.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modelowanie podwykonawstwa w przepływie produkcji

W [przepływie produkcji oszczędnej](lean-manufacturing-modeling-lean-organization.md) działanie procesu może być zdefiniowane jako podwykonawcze, gdy jest przydzielone do komórki roboczej (grupy zasobów) mającej jeden zasób dostawcy. Gdy komórka robocza jest podwykonawcza, działania odnośnego procesu muszą być połączone z aktywnym wierszem umowy zakupu zawierającym usługę i cenę usługi. Umowa serwisowa na działanie definiuje również obliczenie stosunku ilości produktu w zadaniu Kanban do wynikowej ilości usługi. Można wybrać, czy ilość usługi ma być obliczana na podstawie liczby zadań, ilości dobrego produktu raportowanej w zadaniach czy całkowitej ilości produktu (ta całkowita ilość obejmuje produkty złomowane).  

Również działania przeniesienia mogą być definiowane jako podwykonawcze. Ta definicja następuje niejawnie po zaznaczeniu strony odpowiedzialnej za wysyłkę w działaniu przeniesienia. Jeśli wybrano opcję **Spedytor** lub **Adresat**, a odnośny magazyn źródłowy lub docelowy jest zarządzany przez dostawcę, działanie jest uważane za podwykonawcze. Po wybraniu opcji **Przewoźnik** działanie jest zawsze podwykonawcze. Podobnie jak w podwykonawczych działaniach procesu podwykonawcze działanie przeniesienia musi być połączone z umową serwisową, aby można było aktywować przepływ produkcji.

### <a name="backflush-costing"></a>Wycena wsteczna

Rachunek kosztów pracy podwykonawczej jest całkowicie zintegrowany z wyceną dla rozwiązania dla produkcji oszczędnej (wycena wsteczna). Podczas księgowania przyjęcia usługi określonej z zamówienia zakupu oraz podczas fakturowania koszt usługi jest przydzielany do przepływu produkcji. Dla wyceny wstecznej odchylenie usług podwykonawczych jest obliczane poprzez porównanie bloku podwykonawstwa w koszcie standardowym otrzymanych produktów z rzeczywiście otrzymanymi i zafakturowanymi ilościami usług.

## <a name="material-supply-for-subcontracted-operations"></a>Dostarczanie materiałów do operacji podwykonawczych
Półprodukty i inne pokrewne materiały muszą zostać przeniesione do lokalizacji, gdzie fizycznie jest wykonywana praca. W przypadku używania operacji i działań podwykonawczych takie przeniesienie jest często związane z dodatkowym transportem do lokacji prowadzonej przez dostawcę. Przydzielając materiał w BOM do operacji podwykonawczej, deklarujesz, że materiał musi zostać umieszczony w lokalizacji wejściowej grupy zasobów dla przydzielonego zasobu. Następnie proces planowania głównego lub uzupełnienia zapasów dla produkcji oszczędnej zapewnia przeniesienie materiału do tej lokalizacji.  

W kwestii modelowania zapasów znajdujących się w lokacji dostawcy najlepsza branżowa praktyka stanowi, aby zdefiniować magazyn zarządzany przez dostawcę. Magazyn zarządzany przez dostawcę można łatwo zdefiniować poprzez utworzenie nowego magazynu i przypisanie mu konta dostawcy. Aby udokumentować konieczność przeniesienia tego materiału do dostawcy przed rozpoczęciem operacji, należy przydzielić magazyn zarządzany przez dostawcę do magazynu wejściowego grupy zasobów zawierającej zasób.  

Aby uzupełniać materiał w tym magazynie, można używać wielu strategii:

-   Zamówienia przeniesienia
-   Arkusze przeniesienia
-   Karty Kanban wycofania
-   Bezpośredni zakup do lokalizacji dostawcy

Wyjątkiem od tej reguły są półprodukty. Aby przenieść półprodukty, można użyć tylko następujących opcji:

-   W przypadku zleceń produkcyjnych i szarż produkcyjnych półprodukty mogą być przenoszone tylko logicznie przy użyciu arkusza Lista pobrania ze strony listy **Praca podwykonawcza**. Ten arkusz spowoduje utworzenie dokumentu dostawy, którego można używać do przenoszenia półproduktów i surowców do dostawcy.
-   Dla operacji podwykonawczych w przepływach produkcji przeniesienie półproduktów jest dokumentowane poprzez odbiór kart Kanban wycofania lub produkcji w lokalizacji dostawcy. Aby wymodelować jawne działanie przeniesienia, można zakończyć zadanie Kanban produkcji dodatkowym działaniem przeniesienia.

**Uwaga:** Marszruta produkcji dla jednego zlecenia produkcyjnego może obejmować tylko jedną lokację. Ta reguła dotyczy również prac podwykonawczych. W związku z tym magazyny reprezentujące lokalizacje materiałów zarządzanych przez dostawców muszą być zdefiniowane w tej samej lokacji, co wewnętrzne zasoby używane w marszrucie. Chociaż przepływy produkcji mogą obejmować kilka lokacji, nie umożliwiają transportu półproduktów z jednej lokacji do innej, ponieważ ta operacja pociąga za sobą zmianę kontekstu kosztów.  

Zwykle magazyn wyjściowy i lokalizacja grupy zasobów podwykonawczych są bezpośrednio przydzielane do magazynu i lokalizacji następnego kroku operacji w marszrucie lub przepływie produkcji. Ta konfiguracja pomaga zmniejszyć ilość wykonywanej sprawozdawczości o zadaniach oraz liczbę dodatkowych operacji przeniesienia, które trzeba wymodelować.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]