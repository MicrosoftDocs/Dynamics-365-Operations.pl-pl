---
title: "Przegląd budżetu"
description: "Aby można było tworzyć raporty budżet a wartości rzeczywiste mają prawie każda firma, która używa funkcji Finanse w usłudze Microsoft Dynamics 365 dla operacji. Ten artykuł wyjaśnia minimalnej konfiguracji, które są wymagane do tworzenia budżetów w usłudze Dynamics 365 dla operacji lub wczytać je z innego programu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a639e509cf6a3d2f1b850f27481d7b95546522b8
ms.openlocfilehash: b62e14f7c91692ae97bb332b38b0deeb328cc1bd
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-overview"></a>Przegląd budżetu

Aby można było tworzyć raporty budżet a wartości rzeczywiste mają prawie każda firma, która używa funkcji Finanse w usłudze Microsoft Dynamics 365 dla operacji. Ten artykuł wyjaśnia minimalnej konfiguracji, które są wymagane do tworzenia budżetów w usłudze Dynamics 365 dla operacji lub wczytać je z innego programu.

<a name="overview"></a>Przegląd
--------

Zatwierdzony budżet dla firmy jest przechowywany w dokumencie pod nazwą *wpisu do rejestru budżetu*. Wiersze w dokumencie wpis rejestru budżetu są znane jako *budżetu konta* wpisy i zawierają informacje o wymiarze finansowym, daty i kwoty zatwierdzonego budżetu. Dokument wpis rejestru budżetu jest zintegrowany z podstawowych sprawozdań finansowych i strony dochodzenia porównywania wartości rzeczywiste księgi do kwoty budżetu. 

Istnieje wiele metod tworzenia wpisów do rejestru budżetu w usłudze Dynamics 365 dla operacji:

-   Ręczne wprowadzanie informacji zawartych w dokumencie na stronie **wpisów do rejestru budżetu**.
-   Za pomocą szablonu programu Microsoft Excel, który można otworzyć klikają przycisk **Otwórz w programie Excel** na stronie **wpisów do rejestru budżetu**.
-   Używając jednostki danych **zapisów na koncie budżetu** w module zarządzania danymi w celu zaimportowania wpisów do rejestru budżetu. Należy rozważyć przy użyciu tej metody i włączając **zestaw opartych** ** przetwarzania ** parametr podczas należy zaimportować wiele zapisów na koncie budżetu do systemu.
-   Jeśli firma używa funkcji planowania budżetu w celu przygotowania danych budżetu, można użyć procesu okresowego **Generowanie wpisu do rejestru budżetu**.

Wpis do rejestru budżetu jest uznawane za zakończone po zaktualizowaniu salda budżetu. Na **wpisów do rejestru budżetu** kliknij przycisk **Aktualizuj salda budżetu** dla wybranego budżetu zarejestrować wpis lub wiele wpisów. Po zaktualizowaniu sald budżetu stan wpisu do rejestru budżetu zmienia się na **Zakończono**. Zakończonego wpisu do rejestru budżetu nie można ponownie otworzyć w celu edycji. Dlatego w przypadku konieczności skorygowania danych budżetu należy utworzyć nowy wpis do rejestru budżetu, a nie poprawiać dane w zakończonym wpisie.

## <a name="configuration"></a>Konfiguracja
Konfigurowanie budżetowania należy rozpocząć na stronie **Parametry budżetowania**. Na tej stronie należy utworzyć Arkusz budżetu, liczbę sekwencji dla wpisów do rejestru budżetu oraz domyślne zachowanie w obszarach roboczych.

Następnie, jeśli są zasady kierujące zatwierdzaniem wpisów do rejestru budżetu, w zależności o typu budżetu (np. przeniesienia lub korekty), należy utworzyć przepływy pracy wpisów do rejestru budżetu na stronie **przepływów pracy budżetowania**. Jeśli istnieją scenariusze, w których mogą występować przeniesienia bez konieczności zatwierdzania przepływów pracy, można zdefiniować reguły przeniesienia budżetu do obsługi tych scenariuszy. 

Na stronie **wymiary budżetowania** należy wybrać wymiary finansowe, które są będą używane do budżetowania, na podstawie wymiarów wykorzystywanych w planie kont. Można wybrać wszystkie wymiary finansowe lub ich podzbiór dla budżetowania.

Definiowanie * model budżetu * odnosi się do wszystkich lub niektórych budżetów. Można używać jednego modelu budżetu dla wszystkich wpisów do rejestru budżetu. Można również utworzyć oddzielne modele, które są oparte na typie budżetu, lokalizacji geograficznej lub innym sposobie klasyfikacji budżetu. 

> [!NOTE] 
> Jeśli kontrola budżetu jest używany, można skojarzyć tylko jeden model budżetu z cyklem budżetu określonego zakresu czasu. 

Należy utworzyć *kody budżetu *określające typ transakcji budżetu na potrzeby zapisywania wszelkich powiązanych przepływów pracy. Kody budżetu mogą obsługiwać następujące typy budżetu:

-   Budżet pierwotny
-   Przenieś
-   Wersja
-   Przyszłe zobowiązanie wiążące
-   Przyszłe zobowiązanie niewiążące
-   Budżet przeniesiony na późniejszy okres

Kody budżetu pozwalają prowadzić dziennik inspekcji modyfikacji zatwierdzonego budżetu w toku cyklu budżetu. Jeśli przepływ pracy jest związany z kodem budżetu, przepływ pracy zostanie włączona dla wszystkich wpisów do rejestru budżetu przy użyciu tego kodu budżetu i czynności przepływu pracy musi zostać wykonane zanim dotrą wpis do rejestru budżetu **zakończone** etapu.  

Można też opcjonalnie skonfigurować *reguły przeniesienia budżetu*. Aby użyć reguły przeniesienia budżetu, wybierz **Użyj reguł dla przeniesień budżetu** na **parametry budżetu** strony. Gdy reguły przeniesienia budżetu są używane, jeśli użytkownik tworzy dokument za pomocą kodu budżetu typu **Przeniesienie**, salda budżetu nie będą aktualizowane w przypadku naruszenia reguł przeniesienia budżetu. Na przykład można zezwolić na korzystanie z dokumentów przeniesienia, w których budżet wydatków jest przenoszony między głównymi kontami w dziale sprzedaży i marketingu, ale można zablokować przenoszenie budżetu z lub do tego działu do momentu zatwierdzenia przepływu pracy dla tego typu wpisu do rejestru budżetu.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Korzystanie z obszarów roboczych i stron zapytania do śledzenia budżetu i wartości rzeczywistych
Menedżer budżetu może sprawdzić bieżący stan budżetu w obszarze roboczym **Budżety i prognozy księgi**. Karty **Wydatki przekraczające budżet** i **Przychody poniżej budżetu** zawierają szybki widok kombinacji wymiaru finansowego, gdzie cele budżetu nie zostały osiągnięte lub zbliżają się do progu. Można dostosować wartość procentowa progu budżetu i zestawy wymiarów finansowych, które są używane na tych kartach, klikając **Konfiguruj mój obszar roboczy**. Można kliknąć opcję **Menedżerowie jednostki**, aby wyświetlić pracowników odpowiedzialnych za określone kombinacje wymiarów finansowych wybrane na tych kartach. Na przykład, jeśli zobaczysz, że budżet wydatków działu operacji przekracza próg, możesz łatwo znaleźć menedżera działu operacji i skontaktować się z nim w celu omówienia problemu. 

> [!NOTE] 
> **Kierownik działu** w **jednostek organizacyjnych** strona określa menedżerowie, które obsługują kombinacje określonych wymiarów finansowych. Kliknij opcję **Zobacz więcej** u dołu karty, aby otworzyć stronę zapytań **Budżet a wartości rzeczywiste** w celu uzyskania dodatkowych informacji o kwotach budżetu w porównaniu z rzeczywistymi wartościami. 

Strona zapytań **Budżet a wartości rzeczywiste** pozwala przejść do szczegółów budżetu w porównaniu z wartościami rzeczywistymi. Wybierz wiersz na stronie zapytania, a następnie kliknij przycisk **Salda okresowe**, aby wyświetlić wartości rzeczywiste w podziale na okresy obrachunkowe. Strona **Zapisów na koncie budżetu** umożliwia przeglądanie szczegółowych kwot budżetu we wpisach do rejestru budżetu. Strona **Zapisy w arkuszu finansowym **otwiera transakcje księgi uwzględnione w obliczonej kwocie **rzeczywistej**. 

Firma, która korzysta z funkcji planowania budżetu może tworzyć i używać *prognoz budżetowych *w obszarze roboczym **Budżety i prognozy księgi**.


