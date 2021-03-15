---
title: Przegląd budżetu
description: Prawie każda firma, która używa funkcji finansowych w Microsoft Dynamics 365 Finance, będzie musiała mieć możliwość tworzenia raportów porównujących kwoty budżetowe z rzeczywistymi. Ten artykuł wyjaśnia minimalną konfigurację niezbędną do tworzenia budżetów w Finance and Operations lub ich wczytywania z innych programów.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ab9c91c365be647f336f5eca297c9107f20d0c9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978971"
---
# <a name="budgeting-overview"></a>Omówienie budżetu 

[!include [banner](../includes/banner.md)]

Prawie każda firma, która używa funkcji finansowych w Microsoft Dynamics 365 Finance, będzie musiała mieć możliwość tworzenia raportów porównujących kwoty budżetowe z rzeczywistymi. Ten artykuł wyjaśnia minimalną konfigurację niezbędną do tworzenia budżetów w Finance and Operations lub ich wczytywania z innych programów.

<a name="overview"></a>Omówienie
--------

Zatwierdzony budżet dla firmy jest przechowywany w dokumencie pod nazwą *wpisu do rejestru budżetu*. Wiersze dokumentu wpisu rejestru budżetu są nazywane zapisami *konta budżetu* i zawierają informacje o wymiarach finansowych, datach i kwotach zatwierdzonego budżetu. Dokument z wpisami rejestru budżetu jest zintegrowany z podstawowymi raportami finansowymi oraz stronami zapytań, na których porównywane są rzeczywiste kwoty w księgach z kwotami ustalonymi w budżecie. 

Istnieje wiele metod tworzenia wpisów do rejestru budżetu:

-   Ręczne wprowadzanie informacji zawartych w dokumencie na stronie **wpisów do rejestru budżetu**.
-   Za pomocą szablonu programu Microsoft Excel, który można otworzyć klikają przycisk **Otwórz w programie Excel** na stronie **Wpisy do rejestru budżetu**.
-   Używając jednostki danych **zapisów na koncie budżetu** w module zarządzania danymi w celu zaimportowania wpisów do rejestru budżetu. Rozważ użycie tej metody i włączenie parametru **Przetwarzanie** **oparte na zestawie**, jeśli musisz zaimportować do systemu wiele zapisów na koncie budżetu.
-   Jeśli firma używa funkcji planowania budżetu w celu przygotowania danych budżetu, można użyć procesu okresowego **Generowanie wpisu do rejestru budżetu**.

Wpis do rejestru budżetu jest uważany za zakończony, gdy salda budżetu zostaną zaktualizowane. Na stronie **Wpisy do rejestru budżetu** kliknij przycisk **Aktualizuj salda budżetu** dla wybranego wpisu do rejestru budżetu lub dla wielu wpisów. Po zaktualizowaniu sald budżetu stan wpisu do rejestru budżetu zmienia się na **Zakończono**. Zakończonego wpisu do rejestru budżetu nie można ponownie otworzyć w celu edycji. Dlatego w przypadku konieczności skorygowania danych budżetu należy utworzyć nowy wpis do rejestru budżetu, a nie poprawiać dane w zakończonym wpisie.

## <a name="configuration"></a>Konfiguracja
Konfigurowanie budżetowania należy rozpocząć na stronie **Parametry budżetowania**. Na tej stronie należy utworzyć Arkusz budżetu, liczbę sekwencji dla wpisów do rejestru budżetu oraz domyślne zachowanie w obszarach roboczych.

Następnie, jeśli są zasady kierujące zatwierdzaniem wpisów do rejestru budżetu, w zależności o typu budżetu (np. przeniesienia lub korekty), należy utworzyć przepływy pracy wpisów do rejestru budżetu na stronie **przepływów pracy budżetowania**. Jeśli istnieją scenariusze, w których mogą występować przeniesienia bez konieczności zatwierdzania przepływów pracy, można zdefiniować reguły przeniesienia budżetu do obsługi tych scenariuszy. 

Na stronie **wymiary budżetowania** należy wybrać wymiary finansowe, które są będą używane do budżetowania, na podstawie wymiarów wykorzystywanych w planie kont. Można wybrać wszystkie wymiary finansowe lub ich podzbiór dla budżetowania.

Należy określić *model budżetu* odnoszący się do wszystkich lub tylko wybranych budżetów. Można używać jednego modelu budżetu dla wszystkich wpisów do rejestru budżetu. Można również utworzyć oddzielne modele, które są oparte na typie budżetu, lokalizacji geograficznej lub innym sposobie klasyfikacji budżetu. 

> [!NOTE] 
> W przypadku korzystania z kontroli budżetu można powiązać tylko jeden model budżetu z jednym okresem cyklu budżetu. 

Należy utworzyć *kody budżetu* określające typ transakcji budżetu na potrzeby zapisywania wszelkich powiązanych przepływów pracy. Kody budżetu mogą obsługiwać następujące typy budżetu:

-   Budżet pierwotny
-   Przenieś
-   Wersja
-   Przyszłe zobowiązanie wiążące
-   Przyszłe zobowiązanie niewiążące
-   Budżet przeniesiony na późniejszy okres

Kody budżetu pozwalają prowadzić dziennik inspekcji modyfikacji zatwierdzonego budżetu w toku cyklu budżetu. Jeśli przepływ pracy jest związany z kodem budżetu, zostanie włączony dla wszystkich wpisów do rejestru budżetu korzystających z danego kodu budżetu, a etapy przepływu pracy muszą być wykonane, zanim wpis do rejestru budżetu przejdzie do etapu **Zakończono**.  

Można też dodatkowo skonfigurować *reguły przeniesienia budżetu*. Aby zastosować reguły przeniesienia budżetu, wybierz opcję **Użyj reguł dla przeniesień budżetu** na stronie **Parametry budżetu**. Gdy reguły przeniesienia budżetu są używane, jeśli użytkownik tworzy dokument za pomocą kodu budżetu typu **Przeniesienie**, salda budżetu nie będą aktualizowane w przypadku naruszenia reguł przeniesienia budżetu. Na przykład można zezwolić na korzystanie z dokumentów przeniesienia, w których budżet wydatków jest przenoszony między głównymi kontami w dziale sprzedaży i marketingu, ale można zablokować przenoszenie budżetu z lub do tego działu do momentu zatwierdzenia przepływu pracy dla tego typu wpisu do rejestru budżetu.

Funkcja wprowadzona w programie Microsoft Dynamics 365 Finance w wersji 10.0.7 (styczeń 2020 r.) dodała możliwości i elastyczność do wpisów rejestru budżetu. Aby włączyć te ulepszenia, przejdź do obszaru roboczego **Zarządzanie funkcjami** i wybierz pozycję **Wpisy rejestru budżetu tylko dla ilości** i/lub **Wpisy rejestru budżetu dla domyślnego typu kwoty**.

Funkcja **Wpisy rejestru budżetu tylko dla ilości** umożliwia zaksięgowanie wpisu rejestru budżetu zawierającego kwoty jako tylko ilości. Można na przykład zaksięgować wpis budżetu z ilością 32 i ceną równą zero, w wyniku czego kwota wyniesie zero. Ilości tej można następnie użyć w kontekście raportu finansowego w celu określenia ceny za ilość. Zauważ, że zapytania i raporty w ramach tej funkcji nie zostały zaktualizowane; funkcja umożliwia jedynie zaksięgowanie kwoty wynoszącej zero.

Funkcja **Wpisy rejestru budżetu dla domyślnego typu kwoty** pozwala, aby domyślny typ kwoty we wpisie rejestru budżetu był inny niż wydatek. Wiersz wpisu rejestru budżetu będzie teraz domyślnie ustawiany na wydatek, jeśli typem konta głównego jest wydatek; będzie domyślnie ustawiany na przychód, jeśli typem konta głównego jest wydatek oraz będzie domyślnie ustawiany na wydatek dla wszystkich innych typów kont.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Korzystanie z obszarów roboczych i stron zapytania do śledzenia budżetu i wartości rzeczywistych
Menedżer budżetu może sprawdzić bieżący stan budżetu w obszarze roboczym **Budżety i prognozy księgi**. Karty **Wydatki przekraczające budżet** i **Przychody poniżej budżetu** zawierają szybki widok kombinacji wymiaru finansowego, gdzie cele budżetu nie zostały osiągnięte lub zbliżają się do progu. Można dostosować wartość procentowa progu budżetu i zestawy wymiarów finansowych, które są używane na tych kartach, klikając **Konfiguruj mój obszar roboczy**. Można kliknąć opcję **Menedżerowie jednostki**, aby wyświetlić pracowników odpowiedzialnych za określone kombinacje wymiarów finansowych wybrane na tych kartach. Na przykład, jeśli zobaczysz, że budżet wydatków działu operacji przekracza próg, możesz łatwo znaleźć menedżera działu operacji i skontaktować się z nim w celu omówienia problemu. 

> [!NOTE] 
> Pole **Menedżer działu** na stronie **Jednostki organizacyjne** określa, którzy menedżerowie obsługują określone kombinacje wymiarów finansowych. Kliknij opcję **Zobacz więcej** u dołu karty, aby otworzyć stronę zapytań **Budżet a wartości rzeczywiste** w celu uzyskania dodatkowych informacji o kwotach budżetu w porównaniu z rzeczywistymi wartościami. 

Strona zapytań **Budżet a wartości rzeczywiste** pozwala przejść do szczegółów budżetu w porównaniu z wartościami rzeczywistymi. Wybierz wiersz na stronie zapytania, a następnie kliknij przycisk **Salda okresowe**, aby wyświetlić wartości rzeczywiste w podziale na okresy obrachunkowe. Strona **Zapisów na koncie budżetu** umożliwia przeglądanie szczegółowych kwot budżetu we wpisach do rejestru budżetu. Strona **Zapisy w arkuszu finansowym** otwiera transakcje księgi uwzględnione w obliczonej kwocie **rzeczywistej**. 

Firma, która korzysta z funkcji planowania budżetu może tworzyć i używać *prognoz budżetowych* w obszarze roboczym **Budżety i prognozy księgi**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]