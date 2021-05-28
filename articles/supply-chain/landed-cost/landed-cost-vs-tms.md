---
title: Koszt z wyładunkiem vs. Zarządzanie transportem
description: Microsoft Dynamics 365 Supply Chain Management udostępnia dwa różne moduły do pracy z transportem, zarządzaniem transportem (TMS) i kosztem dostawy. W tym temacie podsumowano funkcje wspólne dla obu modułów i podkreślono różnice między nimi.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c7bc17cad246f4bdb9c2bc63cbc47d05731ad2ac
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021231"
---
# <a name="landed-cost-vs-transportation-management"></a>Koszt z wyładunkiem vs. Zarządzanie transportem

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management udostępnia dwa różne moduły do pracy z transportem: **Zarządzaniem transportem** (TMS) i **Kosztem dostawy**. W tym temacie podsumowano funkcje wspólne dla obu modułów i podkreślono różnice między nimi. Informacji tych można użyć w celu decydowania, które moduły najlepiej pasują do procesów biznesowych. Może się okazać, że niektóre praktyki biznesowe działają lepiej w przypadku TMS, podczas gdy inne najlepiej sprawdzają się w przypadku kosztów z wyładunkiem. Następnie, w zależności od wymagań firmy, można wybrać opcję używania wyłącznie jednego modułu lub można połączyć te dwa moduły.

Ten temat nie jest kompleksowym przeglądem wszystkich funkcji obu modułów. Zamiast tego podkreśla dostępne funkcje związane z transportem towarów od dostawcy do magazynu firmy, gdzie można je zużyć.

## <a name="terminology-reference-data-and-reporting-differences"></a>Terminologia, dane referencyjne i różnice raportowania

### <a name="terminology-comparison"></a>Porównanie terminologii

TMS i koszt z wyładunkiem używają różnych terminów dla podobnych pojęć. W poniższej tabeli podsumowano te terminy i ich użycie w dwóch modułach.

| Terminologia TMS | Termin kosztu z wyładunkiem | Notatki |
|----------|------------------|-------|
| **Obciążenie pracą**<p>*Ładunek* jest zbiorem wysyłek transportowanych jednocześnie na tej samej jednostce transportu (takiej jak ciężarówka lub statek). Ładunki mogą być zarówno przychodzące, jak i wychodzące.</p> | **Podróż**<p>Zazwyczaj *podróż* to jeden środek transportu, który podróżuje w ramach jednej *podróży*. Podróży mogą zawierać wiele *kontenerów wysyłkowych*, a także może zawierać zamówienia przychodzące z różnych firm w organizacji. Podróże mogą być tylko przychodzące.</p> | W systemie TMS jest również używany termin *identyfikator podróży*, który odwołuje się do pola informacyjnego, w którym można wprowadzić identyfikator. Pole TMS nie jest jednak skojarzone z polem TMS i nie jest ono powiązane z pojęciami *podróży* w obszarze Koszt z wyładunkiem. |
| **Trasa**<p>*Marszruta* jest fizyczną ścieżką transportu z miejsca początkowego do docelowego.</p> | **Podróż**<p>*Podróż* jest fizyczną ścieżką transportu z miejsca początkowego do docelowego. Każda podróż musi być przypisana do podróży klienta.</p> | |
| **Segmenty marszruty**<p>Marszruta może mieć wiele *segmentów marszruty*, z których każdy reprezentuje etap podróży. Trasa może obejmować wielu przewoźników lub usługi, z których każdy jest uważany za segment trasy.</p> | **Etapy**<p>Każda podróż może mieć wiele *etapów*, z których każda reprezentuje etap podróży. Etap może być częścią transportu, obsługi cła lub innego działania.</p> | |
| **Kontenery**<p>*Kontener* może być dowolną paczką lub opakowaniem używanym przez system TMS.</p> | **Kontenery wysyłkowe**<p>*Kontener wysyłkowy* to dosłowny, fizyczny kontener wysyłkowy, znany ze statków kontenerowych.</p> | |
| **Kody asortymentu**<p>W TMS (i innych miejscach w Supply Chain Management) *kody asortymentu* identyfikują typy towarów. Mogą mieć wpływ na taryfy, transportowanie materiałów niebezpiecznych itp.</p> | **Kody asortymentu**<p>W przypadku kosztów z wyładunkiem *kody asortymentu* są ustalane na poziomie firmy. Są one głównie używane do raportowania.</p> | Koszt ziemny może również korzystać z kodów asortymentu używanych dla systemu TMS i innych miejsc w Supply Chain Management. Natomiast kody asortymentu Koszt z wyładunkiem są używane tylko przez koszt z wyładunkiem. |

### <a name="some-reference-data-isnt-shared"></a>Niektóre dane referencyjne nie są udostępniane

WTMS i Koszty z wyładunkiem nie są współużytkowane dane referencyjne dotyczące takich jednostek, jak konfiguracja kosztów, wyjazdy czy trasy podróży czy etapy. W przypadku korzystania z obu modułów należy ponownie utworzyć dane nieużytego odwołania.

### <a name="intercompany-reports-dont-work-with-goods-in-transit"></a><a name="intercompany-reports"></a>Raporty międzyfirmowe nie działają z towarami w tranzycie

Poniższe raporty nie działają w połączeniu z funkcją towarów w drodze, dostarczaną przez funkcję Koszt z wyładunkiem:

- [Raport Sumy międzyfirmowych towarów w drodze](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)
- [Raport Sumy międzyfirmowych towarów w drodze](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)

Raporty te zakładają, że towary są wysyłane do transportu natychmiast po wystawieniu dokumentu dostawy i że są przyjmowane do magazynu z transportu po otrzymaniu. Jednak towary w drodze nie są przetwarzane w ten sposób. W związku z tym, jeśli używasz jednocześnie towarów w tranzycie i funkcji międzyfirmowych, wyniki dla obu tych raportów będą nieprawidłowe.

## <a name="using-the-two-modules-together"></a>Używanie tych dwóch modułów razem

Systemu TMS można używać zarówno do operacji przychodzących, jak i wychodzących. Chociaż koszt dostawy zapewnia większość tych samych podstawowych funkcji, co TMS dla operacji przychodzących, dodaje również pewną funkcjonalność. Z tego względu warto rozważyć użycie systemu TMS w operacjach wychodzących i koszt z wyładunkiem w operacjach przychodzących.

Na ogół nie zaleca się używania obu modułów razem w operacjach przychodzących. Należy używać modułu, który najlepiej spełnia Twoje wymagania. Jeśli te dwa moduły są ze sobą połączone, nie można współdzielić między nimi dokumentów źródłowych. Nie używaj na przykład tego samego zamówienia zakupu dla ładunku w systemie TMS i podróży w kosztach z wyładunkiem. W szczególności należy upewnić się, że system nie będzie tworzyć automatycznie ładunków przychodzących. Jeśli towary z zamówień zakupu są uwzględnione w podróży, nie można ich obsługiwać w ramach ładunku.

## <a name="goods-in-transit"></a>Towar w drodze

Jedną z głównych funkcji kosztu z wyładunkiem jest możliwość przetwarzania towarów w drodze. Przetwarzanie towarów w drodze umożliwia otrzymanie finansowego prawa własności do wysłanych towarów zanim zostaną one fizycznie odebrane w magazynie docelowym. W przypadku handlu międzynarodowego często wymagane jest przetwarzanie towarów w drodze.

### <a name="tms-goods-in-transit-features"></a>Towary TMS w tranzycie

System TMS nie obsługuje obecnie przetwarzania towarów w drodze.

### <a name="landed-cost-goods-in-transit-features"></a>Funkcje kosztów z wyładunkiem w drodze

Przetwarzanie towarów w drodze to podstawowa funkcja kosztu z wyładunkiem i zapewnia następujące funkcje:

- **Towary w magazynach tranzytowych** – Z każdym magazynem w Supply Chain Management można skojarzyć towary w magazynie tranzytowym. Towary są przenoszone do towarów w magazynach tranzytowych po zafakturowaniu oryginalnego zamówienia. Pozycje, które są tam fizycznie zarezerwowane, stają się niedostępne do konsumpcji, dopóki nie zostaną odebrane w ich fizycznym magazynie. Dlatego możesz przejąć finansową własność towarów, fakturując zamówienie zakupu.
- **Towary w tranzycie na koncie księgi głównej** — Koszt z wyładunkiem dodaje określone konto księgowania księgi głównej do profilu księgowania zamówienia zakupu w celu obsługi towarów w trakcie przetwarzania tranzytowego. To konto księgi głównej towarów w tranzycie działa jak konto typu „towary zafakturowane nieotrzymane”. Po zafakturowaniu oryginalnego zamówienia zakupu i utworzeniu towarów w zamówieniu tranzytowym koszt bezpośredniego zamówienia zakupu jest księgowany na koncie księgi głównej w tranzycie do momentu otrzymania towarów w ich ostatecznej fizycznej lokalizacji.
- **Aktualizacje kontroli śledzenia** – W zamówieniach towarów w drodze jest dostępna funkcja kontroli śledzenia w kosztach z wyładunkiem. Kontrola śledzenia umożliwia aktualizację oczekiwanej daty dostawy towarów, gdy są one w drodze. Następnie kontrola śledzenia aktualizuje podróż i skojarzone wiersze zamówienia zakupu. Oczekiwana data dostawy jest następnie dostępna dla planowania głównego i logistyki.
- **Wyzwalanie transakcji nadwyżki/niedoboru** — jeśli wystąpi różnica między oczekiwanymi towarami w wierszu podróży a rzeczywistymi towarami odebranymi w magazynie, koszt z wyładunkiem powoduje rozwiązanie problemu przez utworzenie transakcji nadwyżki/niedoboru. Dzięki temu będzie można zarządzać tymi transakcjami w taki sposób, aby je przetwarzać za pomocą zamówienia zakupu lub arkusza transakcji. Transakcje nadwyżki i niedoboru stanowią łącze z powrotem do podróży, oryginalnym zamówieniem zakupu oraz nowym arkuszem ruchu lub zamówieniem zakupu dla odchylenia.
- **Zamówienia na towary w drodze** — Koszty z wyładunkiem wprowadza nowy dokument źródłowy, który jest nazywany *zamówienie towaru w drodze*. Zamówienie na towary w drodze umożliwia fakturowanie oryginalnego zamówienia zakupu w celu nabycia finansowej własności towarów. Podczas fakturowania zamówienia zakupu nowy dokument źródłowy jest tworzony dla każdego wiersza zamówienia zakupu, który ma kombinację wymiarów magazynowych. Towary są następnie fizycznie przenoszone do magazynu tranzytowego, gdzie są fizycznie zarezerwowane dla towarów w drodze i nie mogą zostać zużyte, chyba że zostaną odebrane dla zamówienia w drodze.

## <a name="miscellaneous-charges-and-shipment-costs"></a>Opłaty dodatkowe i koszty wysyłki

Jednym z najważniejszych aspektów wysyłki i zarządzania wysyłką towarów jest rozpoznawanie kosztów ogólnych skojarzonych z wysyłkami. Te koszty ogólne nie są bezpośrednimi kosztami magazynowymi, które są skojarzone z zamówieniem zakupu oraz wysyłką lub podróży. Są to koszty dodatkowe związane z charakterem transportu towarów od dostawcy do organizacji. Te koszty mogą obejmować koszty transportu związane z wysyłką towarów z jednej lokalizacji fizycznej do innej lokalizacji, lub koszty cła, które są związane z importem towarów od dostawcy zagranicznego.

Koszt z wyładunkiem obsługuje te koszty, tworząc nowy typ struktury kosztów, zwanej *kosztami automatycznymi*. System TMS obsługuje te koszty za pomocą funkcji opłat dodatkowych.

### <a name="tms-charge-and-cost-features"></a>Funkcje opłat i kosztów TMS

System TMS używa opłat dodatkowych do zarządzania kosztami dodatkowymi w ładunkach alokowanych do wierszy powiązanego dokumentu źródłowego. Opłaty te można ustawić na poziomie wiersza zamówienia zakupu lub nagłówka zamówienia zakupu.

W systemie TMS opłaty dodatkowe mogą być naliczane lub dzielone przez wagę, objętość lub ilość zapasów. Opłaty mogą być dzielone przez opłaty za fracht lub usługi dodatkowe. Konieczny będzie dalszy rozwój w celu wykorzystania dodatkowych metod podziału w TMS.

### <a name="landed-cost-charge-and-cost-features"></a>Funkcje kosztów z wyładunkiem i kosztów

Koszt z wyładunkiem zapewnia zestaw funkcji kosztów, które obsługują dodatkowe koszty skojarzone z wysyłką towarów. Te koszty są nazywane kosztami automatycznymi i są stosowane w momencie wstępnego fakturowania wysyłki przy użyciu szacowanej kwoty kosztów. Każdy rodzaj kosztów jest zarządzany we własnym księgowaniu. Po zaksięgowaniu rzeczywistych faktur dla kosztów narzutów szacowane koszty są automatycznie aktualizowane, tak aby odzwierciedlały rzeczywiste koszty.

Ponadto koszty ogólne związane z wysyłką towarów mogą być fakturowane w trakcie podróży z portu pochodzenia lub w dowolnym momencie po ich otrzymaniu. Dzięki temu zużycie towarów jest bardziej elastyczne.

Na poniższej liście przedstawiono pewne pojęcia dotyczące funkcji opłat i kosztów w części Koszty z wyładunkiem:

- **Obszar kosztów** — Koszty i opłaty można przypisywać na różnych poziomach lub do *obszarów kosztów* w podróży. Koszty mogą być stosowane na poziomie podróży i rozbijane na poszczególne czasy w podróży. Ponadto koszty mogą być stosowane na poziomie kontenera, zamówienia zakupu, towaru lub zamówienia przeniesienia. Każda opłata za koszt może być zarządzana osobno w różnych obszarach i jest rozbita na koszty jednostkowe.
- **Metody przydziału** — w ustawieniach Koszt z wyładunkiem jest dostępnych kilka metod przydziału. Opłaty kosztowe mogą być naliczane według ilości, kwoty w złotych, wartości, wagi, objętości, miary lub zdefiniowanej przez użytkownika miary wolumetrycznej.
- **Kontrola rozliczenia/odchylenia** – Opłaty związane z kosztami są ustawiane jako własne typy kodów kosztów w ustawieniach Koszt z wyładunkiem. Każdy typ kodu kosztów umożliwia zdefiniowanie konta rozliczeniowego dla opłat szacowanych oraz kont naliczania i cen zakupu dla różnic między kosztami szacowanmi a kosztami rzeczywistymi. Po początkowym zaksięgowaniu szacowanych kosztów na koncie rozrachunkowym jest księgowana wartość kredytowa. Po zaksięgowaniu rzeczywistych faktur koszty rzeczywiste są księgowane, a szacowane koszty obciążają konto rozrachunkowe.

## <a name="matching-freight-bills-and-invoices"></a>Dopasowanie opłat frachtowych i faktur

### <a name="tms-bill-and-invoice-matching-features"></a>Funkcje dopasowywania rachunków i faktur TMS

System TMS może dopasować opłaty frachtowe zawierające szacowane koszty i faktury do rzeczywistych kosztów transportu. Faktury można otrzymać w formie elektronicznej lub papierowej. Uzgadnianie odchylenia między kosztem szacowanym a kosztem rzeczywistym nie ma wpływu na wycenę zapasów.

Aby uzyskać więcej informacji, zobacz temat [Uzgadnianie frachtu w zarządzaniu transportem](../transportation/reconcile-freight-transportation-management.md).

### <a name="landed-cost-bill-and-invoice-matching-features"></a>Funkcje dopasowywania rachunków kosztów z wyładunkiem i faktur

Koszt z wyładunkiem może dopasować opłaty frachtowe do szacunkowych opłat kosztowych i fakturować faktyczne opłaty za koszty szacunkowe. W momencie fakturowania opłaty transportowe znajdują się w arkuszu faktur, a szacowane koszty są rozliczane z konta rozliczeniowego. Ponadto opłaty z tytułu kosztów rzeczywistych są księgowane w stosunku do kosztu sprzedanych towarów dla towaru, wraz z odchyleniami między szacowanymi opłatami a opłatami rzeczywistymi. Takie działanie pozwala na elastyczność procesu fakturowania.

## <a name="tracking"></a>Śledzenie

Ważną cechą zarówno kosztów TMS, jak i kosztów dostawy jest możliwość śledzenia towarów i określania, gdzie znajdują się w trakcie podróży z miejsca pochodzenia do końcowego magazynu docelowego. Śledzenie umożliwia śledzenie i aktualizowanie lokalizacji towarów oraz oczekiwanego przybycia do magazynu w celu zużycia. Oprócz stanu towarów podczas podróży, koszt z wyładunkiem dostarcza oczekiwane i rzeczywiste daty dla każdego etapu podróży.

### <a name="tms-tracking-features"></a>Funkcje śledzenia systemu TMS

System TMS oferuje ograniczone funkcje śledzenia ładunków przychodzących. Pokazuje daty i umożliwia tworzenie integracji w celu znalezienia dokładnej pozycji (na przykład na stronie **Stan transportu**).

Dla każdego odcinka marszruty można wprowadzać szacowane harmonogramy i czasy przybycia.

### <a name="landed-cost-tracking-features"></a>Funkcje śledzenia kosztów z wyładunkiem

Koszt z wyładunkiem może zapewniać kontrolę śledzenia dla każdej podróży, od portu pochodzenia do miejsca docelowego. Kontrola śledzenia ustawia stan podróży. Status wskazuje, czy podróż odbywa się w drodze, w urzędzie celnym w celu kontroli, czy w lokalnej dostawie w drodze do magazynu końcowego. Stan może być ustawiany na poziomie wiersza zamówienia zakupu, kontenera i nagłówka podróży. W związku z tym masz bardziej szczegółową kontrolę.

Ponadto z każdym etapem wyjazdu jest skojarzona potwierdzona oczekiwana data oparta na określonych terminach realizacji. Potwierdzone i oczekiwane daty dostawy są dodawane do wiersza zamówienia zakupu oraz towarów w drodze do zamówień i mogą być używane w planowaniu głównym i logistyce. Oprócz oczekiwanych dat można również zaktualizować rzeczywiste daty. Kolejne etapy w podróży zostaną odpowiednio zaktualizowane.

## <a name="multi-leg-journeys"></a>Podróże wieloetapowe

Pojęcie podróży określa miejsce, w którym znajdują się towary, i określa stan towarów w drodze. Towary mogą przejść przez kilka etapów podróży, a następnie skojarzyć różne koszty z określonym etapem. Przykładami są koszty transportu związane ze statekem oraz koszty transportu lokalnego z portu do miejsca docelowego.

### <a name="tms-multi-leg-journey-features"></a>Funkcje wielostopniowej podróży TMS

W systemie TMS trasy można podzielić na segmenty tras w celu przedstawienia podróży obejmujących wiele etapów. TMS może przydzielać stawki spot i opłaty dodatkowe do poszczególnych segmentów tras.

Aby uzyskać więcej informacji, zobacz temat [Planowanie tras przewozu frachtu z przystankami](../transportation/plan-freight-transportation-routes-multiple-stops.md).

### <a name="landed-cost-multi-leg-journey-features"></a>Funkcje wieloetapowych podróży dla kosztów z wyładunkiem

Koszt wyładunku stanowi ramy dla przemieszczania towarów z miejsca pochodzenia do miejsca przeznaczenia poprzez szereg odcinków, które są przystankami lub etapami podróży. Odcinki są łączone w celu utworzenia szablonów podróży, które definiują sposób przemieszczania towarów od dostawcy do organizacji.

W każdej części wyjazdu można dodatkowo zdefiniować stan każdego wiersza zamówienia zakupu oraz skojarzone z nim czasy realizacji. Łączny czas realizacji dla wszystkich etapów służy do określenia szacowanej daty dostawy. Jednak w przypadku wyjazdów wieloetapowych wymagane jest przetwarzanie towarów w drodze. Podróżami towarów w podróż można zarządzać w tabeli specyficznej dla kosztu z wyładunkiem.

## <a name="receiving-by-container"></a>Przyjęcie według kontenera

Zarządzanie podziałem towarów i ich przechowywania na środku transportu może być istotne. Towary mogą być przechowywane na środku transportu w jednym kontenerze lub w wielu kontenerach. Odbierane towary są odbierane w kontenerach, a różne kontenery w podróży mogą zostać odebrane w różnych godzinach lub w różnych terminach.

Zarówno system TMS, jak i koszt z wyładunkiem zapewniają funkcje zarządzania przyjęciem towarów do kontenera. System TMS używa koncepcji ładunków do zarządzania towarami, zamówieniami zakupu i zamówieniami przeniesienia skojarzonymi z kontenerem wysyłki. System TMS obsługuje przyjmowanie na podstawie struktury opakowania, która jest odbierana za pośrednictwem wcześniejszego powiadomienia o wysyłce (ASN). W przypadku kosztów z wyładunkiem używana jest koncepcja kontenerów wysyłkowych do przetwarzania zamówień zakupu i kontrolowania kosztów narzutów, które są skojarzone z kontenerem na statku.

### <a name="tms-receiving-by-container-features"></a>Odbiór TMS przez funkcje kontenera

TMS obsługuje przychodzące ASN, wszystkie warianty odbioru za pośrednictwem aplikacji Warehouse Management oraz wszystkie metody odbioru za pośrednictwem klienta Supply Chain Management.

### <a name="landed-cost-receiving-by-container-features"></a>Otrzymywanie kosztów wyładunku według funkcji kontenera

W celu obsługi odbioru przez kontener, Koszt z wyładunkiem tworzy rekordy kontenera wysyłkowego i kojarzy zamówienia zakupu z określonym kontenerem wysyłkowym za pomocą jego identyfikatora kontenera. Koszty ogólne mogą być następnie stosowane do tego kontenera wysyłkowego i rozbijane, tak aby były skojarzone z odpowiednimi zamówieniami zakupu.

Kontenery w kosztach z wyładunkiem mogą być odbierane za pośrednictwem nowego typu przyjęcia, który jest nazywany *przyjęciem towarów w drodze*, za pomocą arkuszy przyjęcia lub przyjęcia za pomocą urządzenia przenośnego. W przypadku korzystania z arkuszy przybycia ilości można zainicjować na pomocą towarów w zamówieniu tranzytowym lub z wierszy oryginalnego zamówienia zakupu w kontenerze. Koszt z wyładunkiem zapewnia dwa typy pracy do odbioru za pośrednictwem aplikacji Warehouse Management.

Koszt z wyładunkiem nie dostarcza ASN dla elektronicznego przyjęcia towarów. Ponadto nie obsługuje przepływów aplikacji Warehouse Management, które przetwarzają przyjęcie ładunku, przyjęcie na numer identyfikacyjny lub przyjęcie mieszanego numeru identyfikacyjnego.

## <a name="rate-shopping-by-vendor"></a>Wyszukanie stawek według dostawców

Wyszukanie stawek umożliwia firmie wybór dostawcy usług transportowych na podstawie najniższej ceny, najszybszej trasy lub połączenia obu czynników.

### <a name="tms-rate-shopping-features"></a>Funkcje wyszukiwania stawek TMS

System TMS umożliwia identyfikowanie dostawców i rozwiązania w zakresie marszrut dla zamówień przychodzących i wychodzących. Można na przykład określić najszybszą trasę lub najtańszą stawkę za wysyłkę.

TMS zapewnia pełną optymalizację zakupów i frachtu poprzez warsztat trasowania stawek, elastyczne opcje oceny za pośrednictwem silnika ratingowego, interfejs API silnika ratingowego do integracji z podmiotami zewnętrznymi oraz obsługę wagi wolumetrycznej.

Aby uzyskać więcej informacji, zobacz temat [Aparaty zarządzania transportem](../transportation/transportation-management-engines.md).

### <a name="landed-cost-rate-shopping-features"></a>Funkcje wyszukiwania stawek kosztów z wyładunkiem

Koszt z wyładunkiem zapewnia tylko ograniczoną obsługę wyszukiwania stawek według dostawców. Chociaż można wprowadzić wartości spedytora, koszt z wyładunkiem nie jest porównywany między wieloma dostawcami.

## <a name="driver-check-incheck-out-with-appointment-scheduling"></a>Ewidencjonowania/wyewidencjonowanie kierowcy z planowaniem terminów

Funkcje ewidencjonowania i wyewidencjonowania kierowcy umożliwiają systemowi monitorowanie przybycia i uniemożliwianie obciążania w dokach załadunkowych.

### <a name="tms-driver-check-incheck-out-features"></a>Funkcje ewidencjonowania i wyewidencjonowywania kierowców TMS

System TMS umożliwia tworzenie *terminów*. Terminy dostawy reprezentują zdarzenia występujące w doku celem przyjęcia zamówienia zakupu, wysyłki zamówienia sprzedaży lub przetwarzania przychodzącego i wychodzącego ładunku w określonym dniu i o określonej godzinie. Terminy zapewniają, że doki są dostępne do załadunku i wyładowywania towarów oraz zapobiegają sytuacji, w której wiele przewoźników dociera w tym samym czasie do lokalizacji.

System obsługuje zezwalanie kierowcom na ewidencję w określonych drzwiach doku.

### <a name="landed-cost-driver-check-incheck-out-features"></a>Funkcje ewidencjonowania i wyewidencjonowywania kierowców dla kosztu z wyładunkiem

Koszt z wyładunkiem może przechowywać oszacowania dla daty i czasu dostarczenia kontenera.

## <a name="transfer-orders-and-additional-costs"></a>Zamówienia przeniesienia i koszty dodatkowe

Często firmy muszą mieć możliwość przenoszenia towarów między magazynami. W przypadku przeniesienia tego typu koszty są z nim skojarzone i może być konieczne rozpoznawanie tych kosztów. W części Koszty z wyładunkiem zamówienia przeniesienia można dodawać do podróży lub środka transportu w celu śledzenia przeniesienia towarów między magazynami lub miejscami, szacowania czasu dostawy i oczekiwanej daty dostawy oraz dodawania kosztów ogólnych do przeniesienia towarów.

### <a name="tms-transfer-order-cost-features"></a>Funkcje kosztu zamówienia przeniesienia systemu TMS

System TMS obsługuje tworzenie opłat frachtowych związanych z przeniesieniami. Chociaż opłaty te można wyświetlić z zamówienia przeniesienia, koszt z wyładunkiem nie jest dodawany do kosztu towaru. Uzgodnienie frachtu jest obsługiwane przez utworzenie opłaty frachtowej opartej na tych opłatach. Ta opłata frachtowa jest następnie porównana z fakturą za fracht od dostawcy.

### <a name="landed-cost-transfer-order-cost-features"></a>Funkcje kosztu zamówienia przeniesienia kosztów z wyładunkiem

Koszt z wyładunkiem umożliwia dodawanie zamówień przeniesienia do środka transportu lub podróży. W ten sposób można dodawać koszty wysyłki do podróży jako rozliczenia magazynowe w momencie przyjęcia zamówienia przeniesienia. Koszty narzutów mogą być fakturowane za rzeczywiste koszty i śledzone w podróży w celu aktualizacji kosztu sprzedanych towarów. Chociaż zlecenia transferu nie wykorzystują towarów w przetwarzaniu tranzytowym w wersji standardowej, można je dodać do podróży. Koszt z wyładunkiem jest dodawany do łącznego kosztu każdego towaru.