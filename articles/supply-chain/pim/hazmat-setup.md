---
title: Ustawianie materiałów niebezpiecznych
description: W tym temacie opisano sposób konfigurowania danych wymaganych do klasyfikowania towarów jako materiałów niebezpiecznych. Podczas tworzenia zamówienia sprzedaży zawierającego towar, który jest zaklasyfikowany jako materiał niebezpieczny, system generuje dokumentację materiału niebezpiecznego dla tego zamówienia sprzedaży, gdy jest on wysyłany.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: db0d78c7a6fa69aa4e0c4c82f92c33daabda073f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983348"
---
# <a name="set-up-hazardous-materials"></a>Ustawianie materiałów niebezpiecznych

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Aby skorzystać z funkcji materiałów niebezpiecznych, należy najpierw skonfigurować dane wymagane do klasyfikowania towarów jako materiałów niebezpiecznych. Następnie, podczas tworzenia zamówienia sprzedaży zawierającego towar, który jest zaklasyfikowany jako materiał niebezpieczny, system generuje dokumentację materiału niebezpiecznego dla tego zamówienia sprzedaży, gdy jest on wysyłany.

## <a name="turn-on-the-hazardous-materials-feature-for-your-system"></a>Włączanie funkcji materiałów niebezpiecznych dla systemu

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie informacjami o produktach*
- **Nazwa funkcji:** *Informacje o produktach niebezpiecznych i dokumentacja wysyłki*

## <a name="hazardous-material-regulations"></a>Przepisy dotyczące materiałów niebezpiecznych

Aby można było skorzystać z procesów dot. materiałów niebezpiecznych, należy najpierw utworzyć rozporządzenie. Rozporządzenia określają sposób tworzenia drukowanego tekstu wysyłki dla danego towaru. Definiują również skojarzone metody dostawy.

Poniżej przedstawiono kilka wspólnych rozporządzeń:

- **ADR** — przepisy dotyczące międzynarodowego przewozu drogowego towarów niebezpiecznych
- **CFR 49** — przepisy w USA dot. przewozu towarów niebezpiecznych
- **IMDG** — Międzynarodowy kodeks ładunków niebezpiecznych (IMDG)
- **IATA** — regulacje dotyczące towarów niebezpiecznych międzynarodowego zrzeszenia przewoźników powietrznych (IATA)

Te przepisy pomagają określić, jakie informacje mają być wyświetlane podczas drukowania tekstu wysyłki dla danego towaru. Można zdefiniować tyle rozporządzeń, ile tylko trzeba.

> [!IMPORTANT]
> Funkcja konfigurowania kodów informacyjnych związanych z materiałami niebezpiecznymi nie powoduje, że firma jest zgodna z przepisami. To tylko narzędzie pomagające budować procesy w firmie.

Zazwyczaj dla określonego trybu transportu jest dostępne rozporządzenie — chodzi o typy transportu takie jak transport morski, transport lądowy lub transport lotniczy. W związku z tym każde rozporządzenie można skojarzyć z trybem dostawy. Metoda dostawy będzie używana przy drukowaniu poszczególnych dokumentów w module Zarządzanie magazynem. W module Zarządzanie magazynem każda wysyłka jest połączona z przewoźnikiem i usługą przewozową skonfigurowaną w module **Transport**. Typ transportu jest także skojarzony z przewoźnikiem i usługą przewozu. Podczas uruchamiania raportu jest używany tryb dostawy umożliwiający wyszukanie tekstu drukowanego, skojarzonego ze zwolnionym towarem.

Te dane konfiguracyjne nie są specyficzne dla pojedynczego podmiotu prawnego (firma). Dlatego można mieć wspólny zbiór informacji o niebezpiecznych materiałach udostępniany w ramach wszystkich firm.

Dla każdego rozporządzenia można zdefiniować listę materiałów i wykorzystać ją jako listę szablonów skojarzoną ze zwalnianymi towarami. Dla każdego rozporządzenia można również zdefiniować konfigurację drukowania. Ustawienia drukowania umożliwiają określenie sposobu konstruowania tekstu wysyłki dla danego towaru. Ustawienia drukowania służą do konstruowania tekstu drukowanego dla zwolnionego towaru.

Aby skonfigurować regulacje dotyczące materiałów niebezpiecznych, należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Przepisy dotyczące materiałów niebezpiecznych**. Na stronie dot. **Rozporządzenia dot. materiałów niebezpiecznych** można utworzyć dowolną liczbę rozporządzeń i skonfigurować każde z nich, używając pól opisanych w poniższych podsekcjach.

### <a name="hazardous-material-regulation-header"></a>Przepisy dotyczące materiałów niebezpiecznych — nagłówek

Każde rozporządzenie ma kod i opis. W poniższej tabeli przedstawiono pola dostępne w nagłówku.

| Pole | opis |
|---|---|
| Kod przepisu | Umożliwia wprowadzenie kodu identyfikującego rekord rozporządzenia dotyczącego niebezpiecznego materiału. |
| opis | Umożliwia wprowadzenie opisu rozporządzenia dot. materiału niebezpiecznego. |

### <a name="print-setup-fasttab"></a>Skrócona karta konfiguracji drukowania

Każdemu rozporządzeniu może być przypisana dowolna liczba ustawień drukowania. Ustawienia drukowania można definiować na skróconej karcie **Konfiguracji drukowania**. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdej konfiguracji drukowania.

| Pole | opis |
|---|---|
| Kolejność | Umożliwia zdefiniowanie kolejności, w jakiej pola będą odwoływały się w tekście wysyłki. |
| Drukowanie pola | Wybierz pole, które ma zostać uwzględnione w tekście wysyłki. Nie wszystkie pola dla materiałów niebezpiecznych będą dostępne do wydrukowania. Dostępne będą tylko wspólne pola używane do definiowania tekstu wysyłki w różnych rozporządzeniach. Należy zdefiniować pierwsze pole wydruku jako separator pól z wartością **Sekwencji** równą *0* (zero), tak aby można było jej użyć jako separatora między innymi polami. Wymagane jest tylko jedno odwołanie do separatora pól.<p>Dostępne są następujące wartości:</p><ul></li><li>**Separator pól** — to pole wydruku jest używane jako separator pól w tekście. Wymagane jest tylko jedno odwołanie do separatora pól w sekwencji. Zazwyczaj wartość **Sekwencji** dla tego pola drukowania powinna wynosić *0* (zero). System będzie szukał separatora pól i użyje na liście pierwszy z nich. Wartość tekstowa użyta w ciągu będzie pochodzić z pola **Drukuj po**.</li><li>**Identyfikacja** — to pole wydruku umieszcza [kod identyfikujący i/lub opis](#identification) w tekście drukowanym.</li><li>**Klasa** — to pole wydruku umieszcza [klasa identyfikująca i/lub opis](#classes) w tekście drukowanym.</li><li>**Przedział** — to pole wydruku umieszcza [przedział identyfikująca i/lub opis](#divisions) w tekście drukowanym.</li><li>**Grupa pakowania** — to pole wydruku umieszcza [grupa pakowania identyfikująca i/lub opis](#packing-group) w tekście drukowanym.</li><li>**Kod tunelu i/lub opis** — to pole wydruku umieszcza [kod tunelu i/lub opis](#tunnel) w tekście drukowanym.</li><li>**Właściwa nazwa wysyłki** — to pole wydruku umieszcza [właściwą nazwę wysyłki](hazmat-items.md#hazmat-description) w tekście drukowanym.</li><li>**Nazwa techniczna** — to pole wydruku umieszcza [nazwę techniczną i/lub opis](#technical-name) w tekście drukowanym.</li><li>**Kategoria transportowa** — to pole wydruku umieszcza [kategoria transportowa i/lub opis](#transport-category) w tekście drukowanym.</li><li>**Załadunek** — to pole wydruku umieszcza [kod załadunku i/lub opis](#stowage) w tekście drukowanym.</li><li>**Stały tekst** — to pole wydruku powoduje wprowadzenie tekstu zdefiniowanego w polu **Stały tekst** dla tego wiersza.</li><li>**Kod etykiety i/lub opis** — to pole wydruku umieszcza [kod etykiety i/lub opis](#label) w tekście drukowanym.</li><li>**Pakowanie lotnicze** — to pole wydruku umieszcza [instrukcje pakowania w transporcie lotniczym i/lub opis](#packing-instruction) w tekście drukowanym.</li><li>**Ilość ograniczona** — to pole drukowania sprawdza, czy towar jest oznaczony jako [towar o ograniczonej ilości](hazmat-items.md#material-management), a jeśli tak jest, umożliwia wprowadzenie tekstu zdefiniowanego w polu **Stały tekst** dla tego wiersza.</li><li>**Opis pakowania** — to pole wydruku umieszcza [opis pakowania](#packing-description) w tekście drukowanym.</li></ul> |
| Drukowanie przed | Wprowadź tekst, który ma być wydrukowany przed zawartością określoną przez ustawienia **Pola drukowania**. |
| Drukowanie po | Wprowadź tekst, który ma być wydrukowany po zawartości określonej przez ustawienia **Pola drukowania**. |
| Drukuj z poprzednimi | To pole wyboru należy zaznaczyć, aby uniemożliwić drukowanie separatora pól między poprzednim a tym polem. To pole wyboru należy zaznaczyć w przypadku pól drukowania, które są opcjonalne lub dołączone do innego pola drukowania. |
| Stały tekst | Jeśli w **Polu drukowania** wybrano **Stały tekst** lub **Ilość ograniczona**, należy wprowadzić tekst, który ma zostać wydrukowany. |
| Uwzględnij w procesie drukowania | Umożliwia wybór wartości wybranego pola wydruku, które mają być drukowane dla tego wiersza. Można wydrukować kod lub opis lub zarówno kod, jak i opis. |

### <a name="mode-of-delivery-fasttab"></a>Skrócona karta metody dostawy

Rozporządzenie jest tabelą udostępnioną i nie jest właściwe dla konkretnej firmy. Jednak metody dostawy są zależne od firmy. Dlatego w przypadku konfigurowania metody dostawy należy wybrać relację między rozporządzeniem, firmą i trybem dostawy.

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Tryb dostawy**.

| Pole | opis |
|---|---|
| Firma | Wybierz firmę, która ma być skojarzona z niniejszym rozporządzeniem. |
| Metoda dostawy | Na podstawie wybranej firmy wybierz metodę dostawy, która powinna być skojarzona z tym rozporządzeniem. |

### <a name="country-fasttab"></a>Skrócona karta Kraj

W celach informacyjnych można wyświetlić listę krajów lub regionów, dla których obowiązuje rozporządzenie. Jednak w przypadku uruchomienia raportów z wysyłek do określenia tego rozporządzenia jest używany tylko tryb dostawy. Podczas przeglądania wydań magazynowych nie ma bezpośredniego połączenia z trybem dostawy. Dostawa może być także skojarzona z przewoźnikiem i usługą przewozu. Podczas definiowania usługi przewoźnika należy ją skojarzyć z trybem dostawy. Ta relacja będzie używana w raportach wysyłek, takich jak list przewozowy, aby znaleźć tekst wydrukowany dla danego towaru.

W poniższej tabeli przedstawiono pole dostępne na skróconej karcie **Kraj**.

| Pole | opis |
|---|---|
| Kraj/region | Wybierz region/kraj wynagrodzeń, jaki ma być przyporządkowany do rozporządzenia. |

## <a name="material-codes"></a><a name="hazmat-codes"></a>Kody materiałów

Kody materiałów określają ustawienia związane z określonym składnikiem niebezpiecznym, który może być uwzględniony w zwalnianym produkcie. Każdy kod materiału należy do określonego rozporządzenia dotyczącego materiałów niebezpiecznych, a jego definicja musi być zgodna z tym rozporządzeniem. Po zastosowaniu kodu materiału do zwolnionego produktu przy użyciu pola **Kod materiału**, wszystkie ustawienia niebezpiecznych materiałów w kodzie materiału są automatycznie stosowane do tego produktu. Proces konfigurowania zwolnionych produktów jest więc szybszy i mniej podatny na błąd.

Aby zarządzać niebezpiecznymi definicjami materiałów, wykonaj następujące kroki.

1. Przejdź do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Przepisy dotyczące materiałów niebezpiecznych**.
2. Wybierz rozporządzenie, dla którego ma zostać skonfigurowana definicja materiału niebezpiecznego.
3. W okienku akcji na karcie **Ustawienia** wybierz opcję **Materiały niebezpieczne**.
4. W polu **Kod materiału** wprowadź kod materiału dla definicji niebezpiecznego materiału. Tę wartość należy wybrać w przypadku zastosowania kodu materiału do zwolnionego produktu.

    Pole **Kod rozporządzenia** to pole do odczytu i zawiera rozporządzenie wybrane w kroku 2.

5. Pozostałe pola na tej stronie służą do tworzenia i konfigurowania każdego materiału niebezpiecznego, który ma zastosowanie do wybranego rozporządzenia. Dostępne pola są podzbiorem pól materiałów niebezpiecznych dostępnych dla poszczególnych zwolnionych produktów. Aby znaleźć więcej informacji, przejdź do [Materiały niebezpieczne w produktach, zamówieniach, wysyłkach i ładunkach](hazmat-items.md).

## <a name="hazardous-material-classification-groups"></a><a name="classification-groups"></a>Grupy klasyfikacji niebezpiecznych materiałów

Każda grupa klasyfikacji materiałów niebezpiecznych definiuje grupę wartości pól, które tworzą szablon. Ten szablon można później wybrać, jeśli informacje o materiale niebezpiecznym zostaną skonfigurowane dla zwolnionego towaru.

Po przypisaniu kodu grupy klasyfikacji niebezpiecznych materiałów do zwolnionego towaru informacje skojarzone z tą grupą klasyfikacji zostaną skopiowane do odpowiednich pól towaru. Dzięki temu można uprościć proces konfigurowania, ustanawiając zbiór powiązanych wartości pól, które często są używane razem.

Te dane konfiguracyjne nie są specyficzne dla pojedynczego podmiotu prawnego. Dlatego można mieć wspólny zbiór informacji o niebezpiecznych materiałach udostępniany w ramach wszystkich firm.

Aby skonfigurować regulacje dotyczące grup klasyfikacji niebezpiecznych, należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Grupa klasyfikacji materiałów niebezpiecznych**. Na stronie dot. **Grupa klasyfikacji materiałów niebezpiecznych** można utworzyć dowolną liczbę grup i skonfigurować każde z nich, używając pól opisanych w poniższych tabelach.

| Pole | opis |
|---|---|
| Kod grupy | Wprowadź kod identyfikacji grupy. |
| opis | Służy do wprowadzania opisu grupy. |
| Kod klasy | Umożliwia skojarzenie [kodu klasy](#classes) materiału niebezpiecznego z grupą. |
| Kod oddziału | Umożliwia skojarzenie [kodu przedziału](#divisions) materiału niebezpiecznego z grupą. |
| Kod grupy załadunkowej | Umożliwia skojarzenie [kodu grupy załadunkowej](#packing-group) z grupą. |
| Kod kategorii transportu | Umożliwia skojarzenie [kodu kategorii transportowej](#transport-category) z grupą. |
| Mnożnik | Umożliwia wprowadzenie mnożnika materiału niebezpiecznego stosowanego do wybranej klasy i oddziału niebezpiecznych materiałów zgodnie z obowiązującym rozporządzeniem. Mnożnik ten jest używany jako część formuły, w której obliczane są *Punkty niebezpiecznego materiału* w ramach ładunku lub wysyłki. Aby uzyskać więcej informacji na temat niebezpiecznych punktów i tego mnożnika, zapoznaj się z tematem [Skrócona karta Zarządzanie materiałami](hazmat-items.md#material-management). |

## <a name="hazardous-material-classes"></a><a name="classes"></a>Klasy materiałów niebezpiecznych

Klasa materiału niebezpiecznego jest zazwyczaj mapowana na listę klas dostarczanych w rozporządzeniu, które jest zgodne z systemem. Na przykład amerykańskie rozporządzenie CFR 49 określa „klasę 3” jako ciecze łatwopalne. Istnieje możliwość skonfigurowania klas odpowiednich dla materiałów, które należy sklasyfikować.

Każda klasa zostanie przypisana do konfiguracji materiałów na liście materiałów powiązanej z tym rozporządzeniem. W razie potrzeby przypiszemy klasę do każdego z zwolnionych pozycji w celu opisania niebezpiecznego charakteru produktu.

Te dane konfiguracyjne nie są specyficzne dla pojedynczego podmiotu prawnego. Dlatego można mieć wspólny zbiór informacji o niebezpiecznych materiałach udostępniany w ramach wszystkich firm.

Niebezpieczne klasy materiałów działają razem z przedziałami, grupami i grupami zgodności w następujący sposób:

- W przypadku przypisywania klasy materiałów niebezpiecznych do zwalnianego towaru należy również przypisać [przydział materiału niebezpiecznego](#divisions).
- Za pomocą klas materiałów niebezpiecznych razem z [grupami materiałów niebezpiecznych](#classification-groups) można utworzyć szablon kodów służących do konfigurowania towarów.
- Można skorzystać z [grup klasyfikacji materiału niebezpiecznego](#compatibility-groups) w celu ustalenia, które klasy i oddziały niebezpieczne mogą być dostarczane razem z grupami.

Aby skonfigurować regulacje dotyczące klas materiałów, należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Przepisy dotyczące klas materiałów**. Na stronie dot. **Klasa materiałów niebezpiecznych** można utworzyć dowolną liczbę klas i skonfigurować każdą z nich, używając pól opisanych w poniższych tabelach.

| Pole | opis |
|---|---|
| Kod klasy | Wprowadź kod identyfikacji klasy. Kod ten jest definiowany dla danego przedmiotu. W przypadku przypisywania niebezpiecznej klasy materiałów do zwolnionego towaru zostanie ona użyta na listach wyszukiwania. |
| opis | Wpisz opis klasy. |

## <a name="hazardous-material-divisions"></a><a name="divisions"></a>Przedziały materiałów niebezpiecznych

Przedział materiału niebezpiecznego jest podzbiorem klasy materiałów niebezpiecznych. Należy przypisać zarówno oddział, jak i klasę do każdego produktu zawierającego materiały niebezpieczne.

W przypadku klas, które nie mają żadnych przedziałów, należy utworzyć przedział, w którym kod jest równy *0*. Na przykład w rozporządzeniu IATA materiały radioaktywne klasy-7 nie mają podziałów podrzędnych. W takim przypadku tworzony jest dział o wartości *0*, który można skojarzyć ze zwalnianym produktem podczas przypisywania klasy.

Te dane konfiguracyjne nie są specyficzne dla pojedynczego podmiotu prawnego. Dlatego można mieć wspólny zbiór informacji o niebezpiecznych materiałach udostępniany w ramach wszystkich firm.

Przedział materiałów niebezpiecznych działa razem z klasami, grupami i grupami zgodności w następujący sposób:

- W przypadku przypisywania przedziału materiałów niebezpiecznych do zwalnianego towaru należy również przypisać [klasę materiału niebezpiecznego](#classes).
- Za pomocą przedziałów materiałów niebezpiecznych razem z [grupami materiałów niebezpiecznych](#classification-groups) można utworzyć szablon kodów służących do konfigurowania towarów.
- Można skorzystać z [grup klasyfikacji materiału niebezpiecznego](#compatibility-groups) w celu ustalenia, które klasy i oddziały niebezpieczne mogą być dostarczane razem z grupami.

Aby skonfigurować regulacje dotyczące przedziałów materiałów niebezpiecznych, należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Przedziały materiałów niebezpiecznych**. Na stronie dot. **Przedziału materiałów niebezpiecznych** można utworzyć dowolną liczbę przedziałów i skonfigurować każdą z nich, używając pól opisanych w poniższych tabelach.

| Pole | opis |
|---|---|
| Oddział | Wprowadź kod, który ma być używany jako numer odwołania dla danego przedziału. |
| opis | Wprowadź opis przedziału. |
| Klasa | Umożliwia wyszukanie i przypisanie klasy, do której należy ten przedział. |

## <a name="hazardous-material-compatibility-groups"></a><a name="compatibility-groups"></a>Grupy zgodności niebezpiecznych materiałów

Grupy klasyfikacji materiałów niebezpiecznych służą do ustalenia, które klasy i przedziały niebezpieczne mogą być dostarczane razem z grupami. Gdy operatorzy tworzą ładunki magazynowe lub wysyłki, mogą uruchomić sprawdzanie zgodności, które wydadzą ostrzeżenie, jeśli ładunek lub wysyłka zawiera towary, które nie należą do tej samej grupy zgodności.

Te dane konfiguracyjne nie są specyficzne dla pojedynczego podmiotu prawnego. Dlatego można mieć wspólny zbiór informacji o niebezpiecznych materiałach udostępniany w ramach wszystkich firm.

Aby skonfigurować regulacje dotyczące grup zgodności materiałów niebezpiecznych, należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Grupa zgodności materiałów niebezpiecznych**. Na stronie **Grupa zgodności materiałów niebezpiecznych** można utworzyć dowolną liczbę grup zgodności i skonfigurować każde z nich, używając pól opisanych w poniższych podsekcjach.

### <a name="hazardous-material-compatibility-group-header"></a>Grupy zgodności niebezpiecznych materiałów — nagłówek grupy

Każda grupa zgodności ma kod i opis. W poniższej tabeli przedstawiono pola dostępne w nagłówku.

| Pole | opis |
|---|---|
| Grupa zgodności | Wprowadź kod identyfikacji dla grupy zgodności |
| opis | Umożliwia wprowadzanie opisu grupy zgodności. |

### <a name="compatibility-group-details"></a>Szczegóły grupy zgodności

Każda grupa klasyfikacji materiałów niebezpiecznych tworzy listę klas i przedziałów materiałów niebezpiecznych, które mogą być wspólnie dostarczane.

| Pole | opis |
|---|---|
| Klasa | Wybierz klasę materiałów niebezpiecznych, która jest zgodna ze wszystkimi innymi klasami w grupie. |
| Oddział | Umożliwia wybranie przedziału dla materiału niebezpiecznego, który należy do wybranej klasy. |

## <a name="hazardous-material-specification-values"></a>Wartości specyfikacji materiałów niebezpiecznych

Firma Microsoft Dynamics 365 Supply Chain Management dostarcza kilka typów specyfikacji dla materiałów niebezpiecznych. Dla każdego typu należy określić scentralizowany zbiór wartości dla każdego odpowiedniego pola. Użytkownicy mogą następnie wybierać spośród tych wartości podczas konfigurowania definicji materiałów niebezpiecznych lub zwalnianych produktów. Supply Chain Management umożliwia gromadzenie stron, na których można ustalić wartości. Każda strona jest przypisana do jednego typu specyfikacji. Aby uzyskać opis wszystkich dostępnych specyfikacji oraz informacje dotyczące sposobu ustalania dostępnych wartości dla tego pola, zapoznaj się z poniższymi podsekcjami.

Jednym z przykładów specyfikacji niebezpiecznych materiałów jest _kod załadunku_, który określa sposób przechowywania danego materiału podczas transportu. Korzystając z informacji zawartych w tej sekcji, można ustalić centralną kolekcję kodów załadunku. Ta kolekcja zostanie następnie przedstawiona użytkownikom na liście rozwijanej, gdy będą ustawiać kod załadunku dla zwalnianego produktu.

Te wartości specyfikacji materiału niebezpiecznego nie są właściwe dla poszczególnych firm, dlatego można uzyskać zbiór wspólnych wartości używanych we wszystkich firmach.

[Kody materiałów](#hazmat-codes) będą używane do ustanowienia wspólnych kolekcji ustawień dla każdej specyfikacji, w ramach tego jak zastosowana jest ona do danego rozporządzenia. Następnie można zastosować odpowiedni kod do każdego zwalnianego produktu w zależności od potrzeb. Aby uzyskać informacje dotyczące sposobu stosowania kodu materiału niebezpiecznego do określonego zwalnianego produktu oraz konfigurowania poszczególnych ustawień tego produktu dla każdej specyfikacji opisanej w tym miejscu, zapoznaj się tematem [Niebezpieczne materiały w produktach, zamówieniach, wysyłkach i ładunkach](hazmat-items.md).

### <a name="hazardous-material-emergency-response"></a>Odpowiedź awaryjna dotycząca materiałów niebezpiecznych

Specyfikacja *Awaryjnego reagowania na sytuacje związane z materiałami niebezpiecznymi* wskazuje, co należy zrobić, jeśli wystąpił problem podczas transportu produktu zawierającego dany materiał niebezpieczny.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Awaryjnego reagowania na sytuacje związane z materiałami niebezpiecznymi**. Na stronie **Awaryjnego reagowania na sytuacje związane z materiałami niebezpiecznymi** można utworzyć dowolną liczbę wartości i skonfigurować każdą z nich przy użyciu kodu klasyfikacji oraz krótkiego opisu.

### <a name="hazardous-material-identification"></a><a name="identification"></a>Informacje identyfikacyjne materiałów niebezpiecznych

Specyfikacja *Identyfikacja materiału niebezpiecznego* identyfikuje klasę lub charakter materiału niebezpiecznego. Wartość ta to zazwyczaj kod, który jest oparty na standardzie ONZ. Każda klasa jest identyfikowana za pomocą kodu i opisu i może określać limity metod transportu. Na przykład, aby zidentyfikować łatwopalny element lub materiał, należy utworzyć klasę materiałów niebezpiecznych, która używa kodu *FL* i zawiera w opisie informacje *Łatwopalne*. Ponadto należy określić, że klasa nie może być transportowana za pomocą transportu lotniczego.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Identyfikacja materiału niebezpiecznego**. Na stronie dot. **Identyfikacji materiałów niebezpiecznych** można utworzyć dowolną liczbę wartości i skonfigurować każdy z nich, używając pól opisanych w poniższych tabelach.

| Pole | opis |
|---|---|
| Identyfikator | Umożliwia wprowadzenie kodu, który będzie używany jako numer referencyjny identyfikujący tę klasę materiału niebezpiecznego. |
| opis | Wpisz opis tej klasy. |
| Ograniczanie transportu powietrznego | To pole wyboru należy zaznaczyć, aby wskazać, że ta klasa materiału niebezpiecznego nie powinna być transportowana w ramach transportu lotniczego. |
| Ograniczanie transportu morskiego | To pole wyboru należy zaznaczyć, aby wskazać, że ta klasa materiału niebezpiecznego nie powinna być transportowana w ramach transportu morskiego. |

### <a name="hazardous-material-label"></a><a name="label"></a>Etykieta materiału niebezpiecznego

Specyfikacja *etykiety materiału niebezpiecznego* wskazuje etykietę dla towaru niebezpiecznego, która musi być stosowana do odpowiednich zwalnianych produktów. Te etykiety opisują sposób obsługi produktu. Załóżmy na przykład, że istnieje produkt zawierający gaz trujący. W tym przypadku należy ustawić kod etykiety reprezentujący etykietę gazu trującego. Ponadto użytkownik tworzy proces biznesowy, dzięki czemu będzie wyszukiwał tej wartości podczas wysyłki produktów.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Etykieta materiału niebezpiecznego**. Na stronie **Etykieta materiału niebezpiecznego** można utworzyć dowolną liczbę etykiet i skonfigurować każdą z nich przy użyciu kodu identyfikacji oraz krótkiego opisu.

### <a name="hazardous-material-packing-descriptions"></a><a name="packing-description"></a>Opisy pakowania materiałów niebezpiecznych

Specyfikacja *Opisu pakowania materiałów niebezpiecznych* wskazuje, w jaki sposób należy zapakować towar niebezpieczny. Na przykład może być konieczne zapakowanie w określony typ bębna stalowego lub może być wymagany inny typ specjalnego opakowania.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Opisy pakowania materiału niebezpiecznego**. Na stronie **Opis pakowania materiału niebezpiecznego** można utworzyć dowolną liczbę opisów pakowania i skonfigurować każdy z nich przy użyciu kodu identyfikacji oraz krótkiego opisu.

### <a name="hazardous-material-packing-group"></a><a name="packing-group"></a>Grupa załadunkowa materiałów niebezpiecznych

Specyfikacja *Grupy pakowania materiałów niebezpiecznych* określa grupę pakowania dla przedmiotów niebezpiecznych. Grupa pakowania umożliwia zdefiniowanie kodu i opisu w celu wskazania, w jaki sposób materiały niebezpieczne muszą być pakowane podczas transportu lub wysyłki. Grupa załadunkowa jest przypisywana do towaru za pośrednictwem **Materiały niebezpieczne produktu**.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Grupy pakowania materiału niebezpiecznego**. Na stronie **Grupa pakowania materiału niebezpiecznego** można utworzyć dowolną liczbę grup pakowania i skonfigurować każdy z nich przy użyciu kodu identyfikacji oraz krótkiego opisu.

### <a name="hazardous-material-packing-instruction"></a><a name="packing-instruction"></a>Instrukcje pakowania materiałów niebezpiecznych

Specyfikacja *Instrukcji pakowania materiałów niebezpiecznych* określa instrukcje pakowania, których należy przestrzegać, gdy dany towar niebezpieczny jest przygotowany do transportu drogą powietrzną.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Instrukcje pakowania materiału niebezpiecznego**. Na stronie **Instrukcje pakowania materiału niebezpiecznego** można utworzyć dowolną liczbę identyfikatorów instrukcji i skonfigurować każdy z nich przy użyciu kodu identyfikacji oraz krótkiego opisu.

### <a name="hazardous-material-stowage"></a><a name="stowage"></a>Rozmieszczenie materiałów niebezpiecznych

Specyfikacja *Załadunku towaru niebezpiecznego* wskazuje sposób, w jaki produkt musi być przechowywany na statku, gdy jest transportowany przez transport morski.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Załadunek materiału niebezpiecznego**. Na stronie **Załadunek materiału niebezpiecznego** można utworzyć dowolną liczbę identyfikatorów załadunku i skonfigurować każdy z nich przy użyciu kodu identyfikacji oraz krótkiego opisu.

### <a name="hazardous-material-transport-category"></a><a name="transport-category"></a>Kategoria transportu materiałów niebezpiecznych

Specyfikacja *Kategorii transportu materiału niebezpiecznego* jest zazwyczaj używana do grupowania podobnych produktów niebezpiecznych w raportach. Na przykład kategorie transportu są używane w raporcie **Podsumowanie wysyłki**, który można wydrukować z poziomu rekordu wydania magazynowego.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Kategorii transportu materiału niebezpiecznego**. Na stronie **Kategoria transportu materiału niebezpiecznego** można utworzyć dowolną liczbę kategorii transportu i skonfigurować każdy z nich przy użyciu wyświetlanej nazwy oraz krótkiego opisu.

### <a name="hazardous-material-technical-name"></a><a name="technical-name"></a>Nazwa techniczna materiału niebezpiecznego

Specyfikacja *Nazwy technicznej materiału niebezpiecznego* umożliwia podanie powszechnie używanej lub wewnętrznej nazwy firmowej opisującej poszczególne materiały.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Nazwa techniczna materiału niebezpiecznego**. Na stronie **Nazwa techniczna materiału niebezpiecznego** można utworzyć dowolną nazwę techniczną i skonfigurować każdą z nich przy użyciu wyświetlanej nazwy oraz krótkiego opisu.

### <a name="hazardous-material-tunnel"></a><a name="tunnel"></a>Tunel materiałów niebezpiecznych

Specyfikacja *Tunelu materiału niebezpiecznego* ogranicza typy tuneli, przez które można przetransportować materiały niebezpieczne, podając zidentyfikowaną listę typów tuneli, które muszą być używane. Kategorie tunelu są ustanawiane przez odpowiednie przepisy dotyczące niebezpiecznych przewozów materiałów. Ta specyfikacja dotyczy zazwyczaj transportu drogowego.

Aby skonfigurować wartości dla tej specyfikacji należy przejść do sekcji **Zarządzanie informacjami o produktach \> Konfiguracja \> Dokumentacja wysyłki dot. materiałów niebezpiecznych \> Tunel materiału niebezpiecznego**. Na stronie **Tunel materiału niebezpiecznego** można utworzyć dowolną liczbę identyfikatorów tunelu i skonfigurować każdy z nich przy użyciu kodu identyfikacji oraz krótkiego opisu.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]