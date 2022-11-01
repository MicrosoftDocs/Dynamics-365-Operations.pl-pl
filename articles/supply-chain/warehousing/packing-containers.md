---
title: Zapakuj kontenery do wysyłki
description: W tym artykule opisano proces pakowania, który pozwala sprawdzić poprawność towarów magazynowych i zapakować je do kontenerów.
author: perlynne
ms.date: 7/13/2022
ms.topic: business-process
ms.search.form: WHSLocationType, WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup, WHSPack, WHSContainerTable,
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 118b1c79d23cd1b5044ede9aa9c469409cd22166
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708791"
---
# <a name="pack-containers-for-shipment"></a>Zapakuj kontenery do wysyłki

[!include [banner](../../includes/banner.md)]

Proces pakowania w kontenery umożliwia sprawdzanie poprawności pozycji magazynowych i pakowanie ich do kontenerów. Podczas tego procesu pracownicy magazynu zazwyczaj pobierają towary z magazynów luzem i przenoszą je do obszaru pakowania. Tam wielu pracowników magazynu sprawdza ilości i rodzaje towarów i przypisuje je do odpowiednich rozmiarów kontenerów. Gdy kontener jest w pełni zapakowany, jest zamykany i przenoszony do obszaru doku wyjściowego, gdzie jest przygotowywany do wysyłki.

Kontenery reprezentują fizyczne struktury, w które pakowane są elementy, a informacje o kontenerach można śledzić w systemie. Informacje te mogą być przydatne podczas planowania transportu, zwłaszcza jeśli obliczasz opłaty za wysyłkę na podstawie kontenerów. Przed wysłaniem możesz wyświetlić liczbę kontenerów używanych w przesyłce, typy używanych kontenerów oraz fizyczne wymiary każdego kontenera (takie jak całkowita objętość i waga).

Z kontenerami można korzystać z kilku powiązanych funkcji magazynu wychodzącego. Aby uzyskać więcej informacji, zobacz następujące artykuły:

- [Konteneryzacja grupy czynności](wave-containerization.md)
- [Sortowanie towarów wychodzących](outbound-sorting.md)
- [Wysyłka małych paczek](small-parcel-shipping.md)
- [Potwierdź i przenieś](confirm-and-transfer.md)
- [Ustawianie różnych wymiarów pakowania i przechowywania](packing-vs-storage-dimensions.md)
- [Praca pakowania do pakowania kontenerów wychodzących i przetwarzania wysyłek](packing-work.md)
- [Pakowanie kontenerów za pomocą aplikacji mobilnej Warehouse Management](warehouse-app-packing-containers.md)
- [Przykładowy scenariusz — Pakowanie kontenerów za pomocą aplikacji mobilnej Warehouse Management](warehouse-app-pack-containers-scenario.md)
- [Drukowanie etykiet kontenera](print-container-labels.md)

## <a name="set-up-your-warehouse-to-use-manual-packing-operations"></a>Skonfiguruj swój magazyn tak, aby korzystał z ręcznych operacji pakowania

Istnieją dwa podstawowe sposoby organizowania operacji wychodzących:

- **Tworzenie i przetwarzanie grupy czynności** – Pracownicy zbierają towary na podstawie wychodzącej pracy magazynowej. Następnie umieszczają produkty bezpośrednio w lokalizacji wysyłki wychodzącej, gdzie są gotowe do natychmiastowej wysyłki. Aby uzyskać informacje o tym, jak skonfigurować i korzystać z tego procesu, zobacz [Tworzenie i przetwarzanie grupy czynności](wave-processing.md).
- **Ręczne pakowanie na stacji pakowania** — ten proces ma dodatkową operację między operacjami pobrania i wysyłki. Zamiast umieszczać inwentarz w *lokalizacji wysyłki drzwi wnęki* , pracownicy umieszczają go w *lokalizacji pakowania*. Następnie zarządzają procesem pakowania w stacji pakowania za pomocą strony **Pakuj** w kliencie sieci web. Aby włączyć ten proces, musisz skonfigurować system zgodnie z opisem w tej sekcji.

### <a name="set-up-warehouse-locations-for-packing"></a>Skonfiguruj lokalizacje magazynowe do pakowania

Musisz mieć co najmniej jedno miejsce pakowania, w którym pracownicy będą umieszczać elementy inwentarza, aby można je było zapakować do kontenerów. Aby uzyskać więcej informacji na temat tworzenia lokalizacji magazynowych, zobacz [Konfigurowanie lokalizacji w magazynie z obsługą WMS](tasks\configure-locations-wms-enabled-warehouse.md). W poniższych podrozdziałach opisano sposób tworzenia i konfigurowania lokalizacji pakowania.

#### <a name="set-up-location-types-for-packing"></a>Skonfiguruj typy lokalizacji do pakowania

Zdefiniuj *typ lokalizacji* dla lokalizacji pakowania. Typy lokalizacji mogą służyć jako opcje filtrowania do kontrolowania różnych procesów zarządzania magazynem. Nazwa każdego typu lokalizacji zazwyczaj opisuje sposób użycia tego typu lokalizacji. Skonfigurowany tutaj typ lokalizacji musi być powiązany z każdą lokalizacją używaną do operacji pakowania.

Wykonaj poniższe czynności, aby skonfigurować typ lokalizacji.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Typy lokalizacji**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać typ lokalizacji do siatki.
1. Ustaw następujące pola dla nowego typu lokalizacji:

    - **Typ lokalizacji** – Wprowadź nazwę typu lokalizacji. Każda nazwa musi być unikalna i powinna opisywać, w jaki sposób ma być używany typ lokalizacji.
    - **Opis** — Wpisz krótki opis typu lokalizacji.

#### <a name="inform-the-system-about-the-packing-location-type"></a>Poinformuj system o typie lokalizacji pakowania

Po utworzeniu typu lokalizacji należy skonfigurować system tak, aby rozpoznawał go jako typ lokalizacji używany do operacji pakowania.

Wykonaj poniższe czynności, aby ustawić typ lokalizacji używany do operacji pakowania.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**
2. Na karcie **Ogólne**, na skróconej karcie **Typy lokalizacji** ustaw w polu **Typ lokalizacji pakowania typ lokalizacji**, który będzie służy do identyfikowania stacji pakowania.

> [!NOTE]
> W przypadku uaktualniania z wersji Microsoft Dynamics AX status *W opakowaniu* został usunięty z przesyłek i ładunków, ponieważ nie działał spójnie i powodował nadmiarowe dane. Dlatego strony listy **W przesyłkach** i **Ładunki w opakowaniu** zostały wycofane. Kontenery, które muszą być zapakowane, są śledzone na poziomie lokalizacji.
>
> W poprzednich wersjach lokalizację pakowania definiowano za pomocą pola **Identyfikator profilu lokalizacji pakowania** na karcie **Pakowanie** strony **Parametry zarządzania magazynem**, aby określić *profil lokalizacji*. W obecnej wersji używasz pola **Typ lokalizacji pakowania** na karcie **Ogólne** na stronie **Parametry zarządzania magazynem**, aby określić *typ lokalizacji*, zgodnie z opisem w tym artykuł. Nowe pole jest lepiej dostosowane do procesu identyfikacji lokalizacji postoju i ostatecznych lokalizacji wysyłki.
>
> Chociaż możesz nadal używać starego pola **Identyfikator profilu do pola Lokalizacja pakowania**, zalecamy zamiast tego zacząć używać nowego pola **Typ lokalizacji pakowania**, ponieważ stare pole zostanie w końcu przestarzałe.
>
> Jeśli usuniesz ustawienia starego pola **Identyfikator profilu dla lokalizacji pakowania**, a następnie zapiszesz stronę, to pole zostanie trwale wyłączone. W przypadku instalacji, w których pole **Profile ID dla lokalizacji pakowania** nigdy nie było używane, będzie ono zawsze wyłączone. Po wyczyszczeniu ustawienia pola **Identyfikator profilu lokalizacji pakowania** użyj ustawień opisanych w tym artykule, aby skonfigurować i zidentyfikować lokalizację pakowania.

#### <a name="set-up-location-profiles-for-packing-locations"></a>Skonfiguruj profile lokalizacji dla lokalizacji pakowania

Każdy *profil lokalizacji* ustala informacje i reguły dotyczące skojarzonych lokalizacji. Ponieważ do operacji pakowania potrzebna jest co najmniej jedna lokalizacja, oprócz typu lokalizacji należy utworzyć dla niej profil lokalizacji. Każdy profil może być używany przez dowolną liczbę lokalizacji. Lokalizacje używane do pakowania muszą być skonfigurowane do śledzenia tablic rejestracyjnych.

Wykonaj poniższe czynności, aby skonfigurować profil lokalizacji dla lokalizacji pakowania.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
1. Wybierz istniejący profil z okienka listy lub wybierz **Nowy** w okienku akcji, aby utworzyć nowy.
1. W nagłówku nowego lub wybranego profilu ustaw następujące pola:

    - **Identyfikator profilu lokalizacji** – Wprowadź unikatowy identyfikator i nazwę dla profilu lokalizacji.
    - **Nazwa** — umożliwia wprowadzenie opisowej nazwy profilu.

1. Na skróconej karcie **Ogólne** ustaw następujące pola:

    - **Format lokalizacji** — umożliwia wybór formatu lokalizacji, który będzie używany dla bieżącej lokalizacji. Formaty lokalizacji to system nazewnictwa używany do tworzenia unikalnych i spójnych nazw dla różnych pozycji składowania lokalizacji używanych w magazynie. Jeśli nie masz jeszcze potrzebnego formatu, możesz go utworzyć, przechodząc do **Zarządzanie magazynem \> Konfiguracja \> Magazyn \> Formaty lokalizacji**. Aby uzyskać więcej informacji, przejrzyj [Konfigurowanie lokalizacji w magazynie z obsługą WMS](tasks/configure-locations-wms-enabled-warehouse.md).
    - **Typ lokalizacji** — Wybierz typ lokalizacji skonfigurowany jako typ lokalizacji pakowania na stronie **Parametry zarządzania magazynem**, zgodnie z opisem we wcześniejszej części tego artykułu.
    - **Użyj opcji śledzenia numeru identyfikacyjnego** — w przypadku lokalizacji pakowania ustaw tę opcję na *wartość Tak*. System musi być w stanie śledzić identyfikatory tablic rejestracyjnych w miejscach pakowania, aby móc kontrolować proces pakowania.
    - **Zezwalaj na ujemny stan magazynowy** — w przypadku lokalizacji pakowania ustaw tę opcję jako *Nie*.
    - **Pozwól na mieszane pozycje** — w przypadku lokalizacji pakowania ustaw tę opcję jako *Tak*. To ustawienie jest wymagane, ponieważ wiele różnych numerów artykułów jest zwykle dostarczanych do miejsc pakowania w tym samym czasie.
    - **Pozwól na mieszane stany zapasów** — w przypadku lokalizacji pakowania ustaw tę opcję jako *Tak*. To ustawienie jest wymagane, ponieważ towary o różnych stanach magazynowych są zazwyczaj dostarczane do lokalizacji pakowania w tym samym czasie.
    - **Pozwól na mieszane partie zapasów** — w przypadku lokalizacji pakowania ustaw tę opcję jako *Tak*. Ta opcja jest automatycznie ustawiana na *Tak* zawsze, gdy opcja **Zezwalaj na elementy mieszane** jest ustawiona na *Tak*.

#### <a name="set-up-packing-locations"></a>Skonfiguruj miejsca pakowania

Musisz mieć co najmniej jedną *lokalizację*, w której pracownicy będą umieszczać elementy inwentarza, które muszą być zapakowane w kontenery.

Wykonaj poniższe czynności, aby dodać lokalizację pakowania.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.
1. W okienku akcji wybierz opcję **Nowe**, aby dodać lokalizację.
1. Ustaw następujące pola dla nowej lokalizacji:

    - **Magazyn** — Określ magazyn, w którym musi istnieć lokalizacja pakowania.
    - **Lokalizacja** – Wprowadź nazwę nowej lokalizacji.
    - **Identyfikator profilu lokalizacji** – Pamiętaj, aby podać identyfikator utworzony w poprzedniej sekcji.

## <a name="set-up-the-packing-process"></a>Skonfiguruj proces pakowania

W tej sekcji opisano, jak skonfigurować ustawienia, które umożliwiają proces pakowania i umożliwiają pracownikom pakowanie zapasów do kontenerów.

### <a name="set-up-container-packing-policies"></a><a name="packing-policy"></a>Ustawianie zasad pakowania kontenerów

Każda *zasada pakowania kontenerów* definiuje sposób przetwarzania kontenera. Za każdym razem, gdy tworzysz nowy kontener, wybierasz również zasady pakowania kontenerów, które mają być do niego zastosowane.

Wykonaj poniższe kroki, aby skonfigurować zasady pakowania kontenerów.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Zasady pakowania kontenera**.
1. Wybierz istniejącą zasadę z okienka listy lub wybierz **Nowy** w okienku akcji, aby utworzyć nowy.
1. W nagłówku nowych lub wybranych zasad ustaw następujące pola:

    - **Zasada pakowania kontenerów** — wprowadź unikatową nazwę zasady.
    - **Opis** – Wprowadź opisową nazwę zasady.

1. Na karcie **Omówienie** ustaw następujące pola. Te pola pozwalają określić, jakie działania należy podjąć, gdy kontener jest zamknięty, czy działać z tworzeniem pracy, czy bez, oraz kiedy kontener powinien zostać zwolniony ze stacji pakowania.

    - **Magazyn** — Wybierz magazyn, w którym obowiązują zasady pakowania.
    - **Domyślna lokalizacja końcowej wysyłki** — umożliwia określenie preferowanej lokalizacji kontenera po jego zamknięciu. To pole jest dostępne tylko wtedy, gdy **Zasady zwalniania kontenerów** są ustawione na *Udostępnij w końcowej lokalizacji wysyłki*.
    - **Domyślna lokalizacja sortowania** — to pole jest używane z funkcjami [sortowania wychodzącego](outbound-sorting.md).
    - **Jednostka wagi** — umożliwia wybór jednostka miary domyślnej dla kontenerów zamkniętych i manifestowanych. Zazwyczaj ta jednostka miary będzie jednostką miary używaną przez wagę na stanowisku pakowania. To pole dotyczy zasad z tworzeniem pracy lub bez niego.
    - **Zasady zamykania kontenera** — umożliwia wybranie jednej z następujących opcji definiującej, co ma się pojawiać po zamknięciu kontenera:

        - *Zwolnienie automatyczne* — Kontener zostanie uznany za zwolniony ze stacji pakowania i zostanie wyzwolona akcja określona w polu **Zasady zwalniania kontenera**.
        - *Opóźnione zwolnienie* — kontener nie zostanie natychmiast zwolniony ze stacji pakowania. Pracownik magazynu musi później go zwolnić ręcznie.
        - *Opcjonalnie* — podczas zamykania kontenera pracownik będzie mógł określić, czy kontener ma zostać zwolniony.

        Jeżeli stacja pakowania obsługuje głównie pojedyncze pojemniki, które są wysyłane bezpośrednio do klientów, najbardziej naturalnym podejściem jest natychmiastowe wydanie pojemników. Jeśli stacja pakowania obsługuje przesyłki składające się z wielu kontenerów lub nawet palet, prawdopodobnie najlepiej będzie opóźnić wydanie, dopóki cała przesyłka lub paleta nie zostanie zapakowana i będzie gotowa do odbioru.

    - **Zasada zwalniania kontenerów** — Wybierz jedną z poniższych opcji, aby określić, co powinno nastąpić, gdy pojemnik zostanie zwolniony z miejsca pakowania:

        - *Udostępnij w końcowej lokalizacji wysyłki* — zaktualizuj kontener do końcowej lokalizacji wysyłki. Jeśli wybierzesz tę opcję, użyj pola **Domyślna lokalizacja końcowej wysyłki**, aby określić preferowaną lokalizację kontenera po jego zamknięciu.
        - *Utwórz pracę, aby przenieść pojemnik ze stacji pakowania* — Utwórz pracę, aby przenieść kontener ze stacji pakowania do miejsca postoju lub bezpośrednio do drzwi zatoki. Pole **Szablon pracy** umożliwia określenie szablonu pracy, który powinien być stosowany podczas tworzenia pracy dla kontenera.
        - *Przypisz kontener do pozycji sortowania wychodzącego* — ta opcja jest używana z funkcjami [sortowania wychodzącego](outbound-sorting.md).

        W większości przypadków zalecamy utworzenie pracy do przenoszenia kontenerów, ponieważ takie podejście lepiej odzwierciedla rzeczywiste procesy ręczne w magazynie. Jednak w przypadku prostych scenariuszy lub sytuacji, w których stacja pakowania znajduje się bezpośrednio w obszarze drzwi zatoki, może być korzystne, aby pojemnik był natychmiast dostępny w docelowym miejscu wysyłki.

    - **Szablon pracy** – Wybierz szablon pracy, który ma zostać zastosowany podczas tworzenia pracy dla kontenera. To pole jest dostępne tylko wtedy, gdy pole **Zasady zwalniania kontenerów** jest ustawione na *Utwórz pracę w celu przeniesienia kontenera ze stacji pakowania* i jest powiązane z typem zlecenia pracy o nazwie *Pobieranie zapakowanych kontenerów*. Aby uzyskać więcej informacji, zobacz [Szablony pracy i dyrektywy lokalizacji](control-warehouse-location-directives.md).

    W pozostałych krokach skonfigurujesz ustawienia związane z *manifestacją*. Manifestowanie to proces określania wagi kontenera, grupy kontenerów lub przesyłki wraz z identyfikatorem śledzenia otrzymanym od dostawcy usług transportowych. Dynamics 365 Supply Chain Management nie integruje się z systemami zewnętrznych dostawców transportu. Zamiast tego pracownicy magazynu muszą drukować etykiety otrzymane od dostawcy usług transportowych, a następnie skanować numer śledzenia po zakończeniu procedury manifestu.

    Ponieważ oczywiste wymagania różnią się w zależności od klienta, a nawet od wysyłki do wysyłki, zasady pakowania pozwalają na znaczną elastyczność w przepływie pracy. Możesz skonfigurować manifesty dla kontenerów, grup kontenerów i przesyłek w dowolnej kombinacji.

    Jeśli używasz wielopoziomowej procedury manifestu, pracownicy muszą zamanifestować wszystkie kontenery przed zamanifestowaniem powiązanej grupy kontenerów i muszą zamanifestować wszystkie grupy kontenerów przed zamanifestowaniem powiązanej wysyłki.

1. Na skróconej karcie **Manifest kontenera** możesz ustawić następujące pola:

    - **Automatyczny manifest przy zamknięciu kontenera** – Ustaw dla tej opcji wartość *Tak*, aby zastosować informacje dotyczące manifestu jako część procesu zamykania kontenera. Jeśli nie korzystasz z integracji transportu, informacje muszą być rejestrowane ręcznie.
    - **Wymagania dotyczące manifestu dla kontenera** — umożliwia wybór jednej z następujących opcji:

        - *Brak* — Nie zostanie użyty żaden proces manifestacji.
        - *Ręcznie* — manifest będzie wymagany przez przepływ pracy pakowania. System nie zezwala na zamknięcie lub zwolnienie kontenera do czasu ukończenia manifestu.
        - *Zarządzanie transportem* — manifestowanie zostanie wykonane za pomocą aparatów stawek zarządzania transportem (TMS). Ponieważ ta opcja wymaga niestandardowego programowania w celu zaimplementowania określonego aparatu dla dostawcy transportu, nie będzie działać od razu w bieżącej wersji.

    - **Drukuj zawartość kontenera** – Ustaw dla tej opcji wartość *Tak*, aby automatycznie drukować raport zawartości kontenera po zarejestrowaniu kontenera jako zamkniętego. Raport można również wydrukować na żądanie.

1. Na skróconej **karcie Manifest** grupy kontenerów w polu **Wymagania manifestu** dla grupy kontenerów wybierz jedną z następujących opcji:

    - *Brak* — manifest grupy kontenerów nie zostanie uwzględniony jako wymaganie w przepływie pracy pakowania.
    - *Ręczne* — manifest grupy kontenerów zostanie uwzględniony jako wymóg w przepływie pracy pakowania. Wszystkie kontenery, które są zawarte w grupie, muszą zostać zamknięte przed manifestacją grupy. Tę opcję należy zaznaczyć, jeśli trzeba wykonać manifest dla każdej grupy kontenerów, która jest pakowana w stacji pakowania. Zwykle wybierana jest ta opcja, jeśli kontenery są pakowane na palecie i cała paleta ma manifest.

    > [!NOTE]
    > Bieżąca wersja nie obsługuje raportów manifestu dla grup kontenerów i nie ma obsługi aparatu TMS dla grup kontenerów.

1. Na skróconej karcie **Manifest przesyłki** możesz ustawić następujące pola:

    - **Oczywiste wymagania dotyczące wysyłki** — umożliwia wybór jednej z następujących opcji:

        - *Brak* — manifest przesyłki nie zostanie uwzględniony jako wymóg w przepływie pracy pakowania.
        - *Ręczne* — manifest przesyłki zostanie uwzględniony jako wymóg w przepływie pracy pakowania. Nie można zwalniać kontenerów do wysyłki, dopóki nie zostanie ukończone manifestowanie.
        - *Zarządzanie transportem* — manifestacja będzie się odbywać za pomocą silników stawek TMS. Ponieważ ta opcja wymaga niestandardowego programowania w celu zaimplementowania określonego aparatu dla dostawcy transportu, nie będzie działać od razu w bieżącej wersji.

        Manifest wysyłki powinien być włączony, jeśli wymagane jest wypełnienie manifestu dla całej wysyłki spakowanej w stacji pakowania. Zwykle jest używany, gdy wymagany jest jeden skonsolidowany manifest, nawet jeśli wysyłka składa się z wielu kontenerów lub grup kontenerów.

    - **Drukuj dokument dostawy** – Ustaw tę opcję *tak*, aby automatycznie wydrukować dokument dostawy jako część manifestu wysyłki. List przewozowy można również wydrukować na żądanie.

### <a name="set-up-container-types"></a>Konfigurowanie typów kontenerów

W trakcie ręcznego procesu pakowania należy utworzyć kontenery, aby można było zapakować do nich towary. Każdy kontener musi być oparty na typie *kontenera*, który definiuje maksymalną objętość fizyczną i wagę kontenera.

Wykonaj poniższe czynności, aby utworzyć typ kontenera.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Kontenery \> Typy kontenerów**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać typ kontenerów.
1. Ustaw następujące pola dla nowego typu kontenera:

    - **Kod typu kontenera** — służy do wprowadzania unikatowego identyfikatora typu kontenera.
    - **Opis** – Wpisz opis nowego typu kontenera.
    - **Tara** – Wprowadź rzeczywistą lub szacunkową wagę kontenera.
    - **Maksymalna waga netto** – Wprowadź maksymalną wagę, jaką pojemnik może pomieścić.

1. W sekcji **Wymiary kontenera**, w **polach Długość**, **Szerokość**, **Wysokość** i **Objętość** wprowadź wymiary fizyczne samego kontenera.
1. W sekcji **Wartości maksymalne**, w **polach Długość**, **Szerokość**, **Wysokość** i **Objętość** wprowadź maksymalne fizyczne wymiary, jakie kontener może obsłużyć.
1. Można zdefiniować dodatkowe atrybuty typów kontenerów skojarzonych z innymi operacjami, w których są one używać. Aby uzyskać więcej informacji, zobacz [Konteneryzacja](wave-containerization.md).

> [!NOTE]
> W przypadku ręcznego procesu pakowania system używa tylko wartości pól **Maksymalna waga netto** oraz wartości pola **Objętość** w sekcji **Maksimum**.

### <a name="set-up-packing-profiles"></a>Konfigurowanie profili pakowania

*Profile pakowania* są wymagane w procesie pakowania. Można je wybrać lub ustawić domyślnie po uruchomieniu operacji pakowania na stronie **Pakunek**.

Wykonaj poniższe kroki, aby skonfigurować profil pakowania.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Profile pakowania**.
1. Wybierz istniejący profil z okienka listy lub wybierz **Nowy** w okienku akcji, aby utworzyć nowy.
1. W nagłówku nowego lub wybranego profilu ustaw następujące pola:

    - **Identyfikator profilu pakowania** – Wprowadź unikatowy identyfikator i nazwę dla profilu lokalizacji.
    - **Opis** – Wprowadź opis profilu pakowania.
    - **Zasada pakowania kontenerów** — umożliwia wybór zasad pakowania, które są stosowane w tym profilu. Aby uzyskać więcej informacji, zobacz sekcję [Skonfiguruj zasady pakowania kontenerów](#packing-policy) we wcześniejszej części tego artykułu.
    - **Tryb identyfikatora kontenera** – Wybierz, czy identyfikator kontenera powinien być generowany automatycznie podczas tworzenia kontenera, czy musi być utworzony ręcznie.
    - **Typ kontenera** – Wybierz typ kontenera, który jest używany domyślnie podczas tworzenia nowego kontenera.
    - **Automatyczne tworzenie kontenera przy zamknięciu kontenera** – Zaznacz to pole wyboru, aby automatycznie utworzyć nowy kontener, jeśli poprzedni kontener jest zamknięty, a w bieżącej przesyłce pozostaje co najmniej jeden wiersz.

### <a name="set-up-warehouse-workers"></a>Skonfiguruj pracowników magazynu

Każdy użytkownik lub pracownik, który pakuje kontenery za pomocą strony **Pakuj** klienta WWW lub kodu działania *Pakowanie* w aplikacji mobilnej Warehouse Management, musi mieć konto użytkownika powiązane z *pracownikiem/osobą* odnotować, że wymagane prawa dostępu do zabezpieczeń są przypisane. (Aby uzyskać więcej informacji na temat konfigurowania użytkowników, zobacz [Tworzenie nowych użytkowników](../../fin-ops-core/dev-itpro/sysadmin/tasks/create-new-users.md)).

Aby skonfigurować rekord *pracownika/osoby* dla procesu pakowania, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać użytkownika służbowego.
1. Ustaw pole **Pracownik** na istniejący rekord pracownika, który jest zdefiniowany w module **Zasoby ludzkie** dla użytkownika, który ukończy proces pakowania.
1. Na skróconej karcie **Profil** ustaw następujące pola:

    - **Zasady pakowania kontenerów** — umożliwia wybór zasad pakowania kontenerów, które definiują sposób przetwarzania kontenerów w stacji pakowania. Zasady pakowania kontenerów wybrane w tym miejscu zostaną wstępnie wybrane dla pracownika po otwarciu stacji pakowania. Aby uzyskać więcej informacji, zobacz następujący wpis w blogu: [Poprawiona funkcjonalność pakowania](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611).
    - **Identyfikator profilu pakowania** — umożliwia wybór identyfikatora profilu pakowania, który definiuje stosowane zasady pakowania i ustawienia kontenera. Jeśli wybrany identyfikator profilu pakowania jest skojarzony z zasadami pakowania kontenerów, nie będzie można zmienić ustawienia **Zasady pakowania kontenerów** na tej stronie.

1. Na skróconej karcie **Domyślna stacja pakowania** wybierz domyślną lokalizację, magazyn i lokalizację, które mają zastosowanie do pracownika.
1. Jeśli pracownik będzie używać aplikacji mobilnej Zarządzanie magazynem do zarządzania i rejestrowania swoich prac związanych z pakowaniem kontenerów, na skróconej karcie **Użytkownicy** skonfiguruj jedno lub więcej kont, za pomocą których pracownik może logować się do aplikacji. Aby uzyskać więcej informacji zobacz temat [Konta użytkownika urządzenia przenośnego](mobile-device-work-users.md).

## <a name="example-scenario"></a><a name="scenario"></a>Przykładowy scenariusz

W tej sekcji przedstawiono przykładowy scenariusz tworzenia zamówienia i pakowania towarów.

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/fin-ops/get-started/demo-data.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

Tych scenariuszy można również używać jako wskazówek dotyczących korzystania z danej funkcji podczas pracy w produkcji. Jednak w takim przypadku należy podstawić własne wartości dla każdego ustawienia opisanego w tym polu.

### <a name="sign-in-as-a-user-that-can-do-packing-work"></a>Zaloguj się jako użytkownik, który może pracować przy pakowaniu

Zaloguj się do Supply Chain Management przy użyciu konta użytkownika, które ma uprawnienia wymagane do pakowania kontenerów. Użytkownik *Julia Funderburk* jest częścią danych demonstracyjnych i ma wymagane uprawnienia. Ten użytkownik ma identyfikator użytkownika *Administrator*.

### <a name="create-a-sales-order-and-complete-the-work"></a>Utwórz zamówienie sprzedaży i zakończ pracę

Aby utworzyć zamówienie sprzedaży i ukończyć pracę przenoszenia zamówionych towarów do stacji pakowania, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz *US-005*.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.
1. Nowe zamówienie sprzedaży zostanie otwarte i będzie zawierało jeden, pusty wiersz na skróconej karcie **wiersze zamówienia sprzedaży**. Ustaw następujące wartości dla nowego wiersza zamówienia:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *2*
    - **Oddział:** *6*
    - **Magazyn:** *62*

1. Gdy wiersz zamówienia jest nadal zaznaczony, wybierz **Zapasy \> Rezerwacja** na pasku narzędzi **Wiersze zamówienia sprzedaży** skróconej karty.
1. Na stronie **Rezerwacja**, w okienku akcji wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

    Zostanie wyświetlony komunikat o identyfikatorze wysyłki i grupy czynności dla zamówienia.

1. Gdy wiersz zamówienia jest nadal zaznaczony, wybierz **Magazyn** \> **Szczegóły pracy** na pasku narzędzi **Wiersze zamówienia sprzedaży** skróconej karty. Jeśli do uruchamiania grup pracy jest uruchamiane przetwarzanie wsadowe, może być konieczne oczekiwanie na krótki czas na proces tworzenia pracy.
1. Na stronie **Praca** w okienku akcji na karcie **Praca** wybierz **Wykonaj pracę**.
1. Na stronie **Zakończenie pracy** w polu **Identyfikator użytkownika** wybierz *62*.
1. Następnie w okienku akcji wybierz pozycję **Weryfikuj pracę**.
1. Po otrzymaniu komunikatu z komunikatem, że praca jest prawidłowa, wybierz opcję **Wykonaj pracę**, aby zakończyć proces pobierania towarów magazynowych i umieszczania ich w lokalizacji *pakowania*.
1. Zanotuj wartość **identyfikatora wysyłki**, która jest wyświetlana dla pracy w górnej siatce.

### <a name="pack-the-ordered-items-into-a-container"></a>Zapakuj zamówione towary do kontenera

Towary magazynowe zostały teraz przywiezione do obszaru pakowania i są gotowe do zapakowania do kontenerów. Wykonaj poniższe czynności, aby utworzyć nowy kontener w systemie i spakować go.

1. Przejdź do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Pakunek**.
1. W oknie dialogowym **Wybieranie stacji pakowania** ustaw następujące wartości:

    - **Oddział:** *6*
    - **Magazyn:** *62*
    - **Lokalizacja:** *Pakiet*
    - **Identyfikator profilu pakowania:** *WH62*

1. Kliknij przycisk **OK**.
1. Na stronie **Pakiet**, w polu **Numer identyfikacyjny lub wysyłka**, wprowadź zanotowany wcześniej identyfikator przesyłki. Na skróconej karcie **Otwarte wiersze** powinny być teraz widać pozostałe rozpakowane towary.
1. W okienku akcji wybierz opcję **Nowy kontener**, aby utworzyć kontener w systemie.
1. W oknie dialogowym **ID nowego kontenera** ustaw pole **Typ kontenera** na *SmallBox*.
1. Wybierz przycisk **OK**, aby utworzyć kontener.
1. Wybierz przycisk **OK**, aby powrócić do strony **Pakuj**. Na skróconej karcie **otwartych kontenerów** jest teraz przedstawiana **wartość identyfikatora kontenera** utworzonego przez użytkownika.
1. W tym scenariuszu zapakuj tylko jeden z zamówiony towarów. Na skróconej karcie **Pakowanie przedmiotów** ustaw następujące wartości:

    - **Ilość:** *1.00*
    - **Identyfikator:** *A0001*

    Natychmiast po wybraniu wartości **Identyfikator** strona aktualizuje skrócone **Otwarte wiersze** i **Wszystkie wiersze**, aby wskazać, że jeden towar został zapakowany. Należy zapakować jedną z dwóch sztuk towaru *A0001*.

1. W okienku akcji wybierz opcję **Zamknij kontener**.
1. W oknie dialogowym **Zamknij kontener** wybierz opcję **Pobierz wagę z systemu**, aby wypełnić domyślną wartość **Waga brutto**.
1. Kliknij przycisk **OK**, aby zamknąć kontener.

> [!TIP]
> Istnieją różne sposoby wyświetlania kontenerów w zależności od kontekstu. Na przykład przy pakowaniu wysyłki często pomocne może być wyświetlenie kontenerów, które są częścią wysyłki, albo wszystkich kontenerów fizycznie w stacji pakowania. Strona **stacji pakowania** zawiera przyciski, których można używać do wyświetlania wszystkich otwartych i zamkniętych kontenerów w stacji pakowania. Widoki te nie są ograniczone do określonej wysyłki. Mogą one być bardzo pomocne w sytuacjach, gdy jeden pracownik pakuje kontener, a inny pracownik manifestuje i zwalnia kontener.
>
> Dostępny jest również skonsolidowany widok wszystkich kontenerów. Ten widok jest najczęściej przydatny dla użytkowników, którzy działają poza kontekstem jednej stacji pakowania. Przejdź do **Zarządzanie magazynem \> Pakowanie i konteneryzacja \> Kontenery**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
