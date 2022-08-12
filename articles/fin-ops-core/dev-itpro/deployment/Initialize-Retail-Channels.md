---
title: Inicjowanie Commerce Scale Unit (chmura)
description: Ten artykuł wyjaśnia, jak zainicjować Commerce Scale Unit (cloud) w Microsoft Dynamics 365 Commerce.
author: jashanno
ms.date: 07/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2018-4-30
ms.openlocfilehash: 93fbf2893fecc7b731f946797907bce4f8448309
ms.sourcegitcommit: 8032d6275e6d9994ef9759ee16e743b483f7689e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183372"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>Inicjowanie Commerce Scale Unit (chmura)

[!include[banner](../includes/banner.md)]

Ten artykuł wyjaśnia, jak zainicjować Commerce Scale Unit (cloud) w Microsoft Dynamics 365 Commerce.

Jeśli korzystasz ze środowiska sandbox warstwy 2 lub środowiska produkcyjnego, które ma aplikację w wersji 8.1.2.x lub nowszej, musisz zainicjować Commerce Scale Unit (chmura), zanim będziesz mógł korzystać z funkcjonalności kanału detalicznego w punktach sprzedaży (POS) lub w operacjach e-commerce, które korzystają z serwera Retail w chmurze. Inicjalizacja utworzy jednostkę Commerce Scale Unit (chmura).

> [!IMPORTANT]
> Dla obecnych klientów korzystających z funkcjonalności kanałów detalicznych w chmurze, aby zapewnić ciągłe i nieprzerwane wsparcie dla Twojego biznesu, wymagamy, abyś zaktualizował swoje kanały detaliczne tak, aby korzystały z Commerce Scale Unit. Nowe środowiska wdrożone bez Commerce Scale Unit nie będą już otrzymywać aktualizacji jakości i usług dla komponentów kanału detalicznego w chmurze. Nie jest wymagane żadne działanie dla klientów, którzy korzystają wyłącznie z Commerce Scale Unit (własny serwer). Skontaktuj się ze swoim architektem rozwiązań Microsoft FastTrack, jeśli potrzebujesz przedłużenia.

## <a name="prerequisites"></a>Wymagania wstępne

1. Wdrożenie środowiska piaskownicy warstwy 2 lub środowiska produkcyjnego, które posiada wersję 8.1.2.x lub nowszą.
2. Możesz samodzielnie wdrożyć do 2 jednostek Commerce Scale Units na środowisko. Jeśli potrzebujesz więcej niż 2 jednostki Commerce Scale Unit na środowisko, w Microsoft Dynamics Lifecycle Services (LCS) utwórz zgłoszenie do pomocy technicznej i wpisz **Prośba o dodatkową jednostkę Commerce Scale Unit** oraz wskaż identyfikator środowiska, liczbę jednostek Commerce Scale Unit i pożądane regiony centrów danych. Wniosek zostanie rozpatrzony w ciągu pięciu dni roboczych. Jeśli nie potrzebujesz więcej niż 2 jednostki Commerce Scale Unit na środowisko, nie musisz tworzyć zgłoszenia do pomocy technicznej. 
3. Musisz mieć uprawnienia Właściciel projektu w Lifecycle Services zanim będziesz mógł zainicjować jednostkę Commerce Scale Unit.
4. Upewnij się, że klucze konfiguracji licencji detalicznych są włączone w twoim środowisku. Więcej informacji: [Raport kodów licencji i kluczy konfiguracji](../sysadmin/license-codes-configuration-keys-report.md). Aby móc korzystać z Commerce Scale Unit, musisz mieć włączone następujące klawisze.

    - RetailBasic
    - RetaileCommerce – jeśli zamierzasz używać e-commerce dla Dynamics 365 Commerce.
    - RetailGiftCard – jeśli chcesz używać kart upominkowych.
    - RetailInvent – w przypadku planowania użycia zapasów.
    - RetailModernPos – jeśli użytkownik planuje używać punkt sprzedaży (POS).
    - RetailReplenishment – w przypadku planowania użycia uzupełniania zapasów.
    - RetailScheduler
    - RetailStores – jeśli zamierzasz korzystać z programu POS.


## <a name="region-availability"></a>Dostępność regionalna
Commerce Scale Unit jest dostępne do wdrożenia w następujących regionach.

| Lokalizacja globalna | Region              | Dostępność        | Komentarze                  |
|-----------------|---------------------|---------------------|---------------------------|
| AMERYKI        | Wschodnie stany USA             | Ogólnie dostępne |  Brak komentarzy                         |
| AMERYKI        | Wschodnie stany USA 2           | Ogólnie dostępne |  Brak komentarzy                          |
| AMERYKI        | Północno-środkowe stany USA    | Ograniczone zdolności produkcyjne    |  Brak komentarzy                            |
| AMERYKI        | Południowo-środkowe stany USA    | Ograniczone zdolności produkcyjne    |  Brak komentarzy                            |
| AMERYKI        | Środkowe stany USA          | Ogólnie dostępne |  Brak komentarzy                            |
| AMERYKI        | Zachodnie stany USA             | Ogólnie dostępne |  Brak komentarzy                            |
| AMERYKI        | Zachodnie stany USA 2           | Ogólnie dostępne |  Brak komentarzy                            |
| AMERYKI        | Kanada środkowa      | Ograniczone zdolności produkcyjne    |  Brak komentarzy                            |
| AMERYKI        | Kanada wschodnia         | Ograniczone zdolności produkcyjne    |   Brak komentarzy                           |
| AMERYKI        | Zachodnie stany USA     | Ograniczone zdolności produkcyjne    |   Brak komentarzy                           |
| APAC            | Australia Wschodnia      | Ogólnie dostępne |   Brak komentarzy                           |
| APAC            | Azja Południowo-Wschodnia      | Ograniczone zdolności produkcyjne | Wdrożenia niedozwolone.    |
| APAC            | Japonia Wschodnia          | Ogólnie dostępne |  Brak komentarzy                            |
| APAC            | Japonia Zachodnia          | Ogólnie dostępne |   Brak komentarzy                           |
| APAC            | Australia Południowo-Wschodnia | Ogólnie dostępne |   Brak komentarzy                           |
| APAC            | Azja Wschodnia           | Ograniczone zdolności produkcyjne    |   Brak komentarzy                           |
| APAC            | Indie południowe         | Ograniczone zdolności produkcyjne | Wdrożenia niedozwolone.    |
| APAC            | Indie środkowe       | Ograniczone zdolności produkcyjne    | Wymaga procesu zatwierdzania. |
| Europa, Bliski Wschód i Afryka (EMEA)            | Europa Zachodnia         | Ograniczone zdolności produkcyjne    | Obecnie nie jest dostępny w LCS. |
| Europa, Bliski Wschód i Afryka (EMEA)            | Europa Północna        | Ograniczone zdolności produkcyjne    | Obecnie nie jest dostępny w LCS. |
| Europa, Bliski Wschód i Afryka (EMEA)            | Południowe Zjednoczone Królestwo            | Ogólnie dostępne |    Brak komentarzy                          |
| Europa, Bliski Wschód i Afryka (EMEA)            | Zachodnie Zjednoczone Królestwo             | Ogólnie dostępne |    Brak komentarzy                          |
| Szwajcaria     | Szwajcaria Północna   | Ograniczone zdolności produkcyjne    | Wymaga procesu zatwierdzania. |
| Zjednoczone Emiraty Arabskie             | Północne Zjednoczone Emiraty Arabskie           | Ograniczone zdolności produkcyjne    | Wymaga procesu zatwierdzania. |

Możliwości rozmieszczenia w regionach o ograniczonych możliwościach są bardzo ograniczone. Prośby o rozmieszczenie są rozpatrywane indywidualnie dla każdego przypadku. Jeśli masz istotną potrzebę biznesową do wdrożenia w regionach o ograniczonej pojemności, możesz złożyć wniosek o wsparcie, aby zostać dodanym do listy oczekujących. Obszary z ograniczeniami zdolności produkcyjnych obecnie nie zezwalają na wdrożenie jednostki Commerce Scale Unit. 

![Mapa pokazująca dostępność regionu.](media/Commerce-Scale-Unit-Region-Availability.png "Mapa pokazująca dostępność regionu")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>Inicjuj Commerce Scale Unit jako część wdrażania nowego środowiska

Upewnij się, że centrala jest dostępna. Jest to wymagane w celu zarejestrowania jednostki skalowania w centrali w trakcie procesu inicjowania. Nie jest zalecane inicjowanie jednostki wagi, gdy centrala jest w trakcie serwisowania, gdyż może ona stać się niedostępna podczas procesu serwisowania.

1. Upewnij się, że środowisko centrali jest dostępne, a nie w trybie [konserwacji](../sysadmin/maintenance-mode.md).
2. W u usługach LCS, na stronie szczegółów środowiska wybierz pozycję **Funkcje środowiska \> Commerce**.
3. Na stronie Wdrożenie konfiguracji handlu wybierz pozycję **Inicjuj**.
4. Wybierz wersję Commerce Scale Unit do zainicjowania.
5. Wybierz region do zainicjowania Commerce Scale Unit.

## <a name="configure-channels-to-use-commerce-scale-unit"></a>Zobacz temat Konfigurowanie kanałów do używania Commerce Scale Unit

Po wdrożeniu Commerce Scale Unit musisz upewnić się, że twoje kanały są skonfigurowane tak, aby korzystać z bazy danych dla niego. 

Aby skonfigurować twoje kanały tak, aby korzystały z bazy danych Commerce Scale Unit, wykonaj poniższe kroki.

1. W centrali rozwiązania Commerce przejdź do opcji **Retail i Commerce \> Ustawienia centrali \> Commerce Scheduler \> Baza danych kanałów**.
1. W lewym okienku wybierz bazę danych kanałów.
1. Na skróconej karcie **Kanał detaliczny** wybierz **Dodaj**, a następnie wybierz swój kanał detaliczny z rozwijanej listy.
1. Wybierz pozycję **Dodaj**, a następnie wybierz kanał online z listy rozwijanej. 

Po zakończeniu przejdź do **Sprzedaż detaliczna i komercyjna \> IT sprzedaży \> Harmonogram dystrybucji** i uruchom zadanie 9999.

> [!NOTE] 
> Zadanie 9999 synchronizuje wszystkie nowe produkty i klientów z Commerce Scale Unit. Proces może potrwać dłuższy czas. Jeśli kanał musi być dostępny tylko dla konfiguracji projektancie stron e-commerce, możesz uruchomić zadanie 1070 zamiast zadania 9999.

### <a name="database-refresh-and-commerce-scale-units"></a>Odświeżanie bazy danych i Commerce Scale Units

Zanim zaczniesz, upewnij się, że znasz [Kroki, które należy wykonać po odświeżeniu bazy danych dla środowisk korzystających z funkcjonalności Commerce](../database/database-refresh.md).

Rekordy bazy danych kanałów jednostek wagi (w formularzu bazy danych kanałów) nie mogą być przenoszone pomiędzy środowiskami w ramach odświeżania bazy danych. Dzieje się tak dlatego, że rekordy reprezentują konfigurację specyficzną dla danego środowiska.

Po odświeżeniu bazy danych możesz zregenerować rekord bazy danych kanałów jednostki wagi poprzez ponowne rozmieszczenie jednostki wagi w LCS. Każda operacja rozmieszczenia lub serwisowania w jednostce wagi będzie próbowała zarejestrować jednostkę wagi w centrali, jeśli zostanie wykryty brak rejestracji.

Możesz dokonać ponownego wdrożenia jednostki wagi bez zmieniania żadnych komponentów, wybierając opcję wdrożenia tej samej wersji, w której znajduje się już twoja jednostka wagi. W LCS można to zrobić w następujący sposób:

1. W u usługach LCS, na stronie szczegółów środowiska wybierz pozycję **Funkcje środowiska \> Retail**.
2. Na stronie konfiguracji obrazu stanowiska wybierz jednostkę wagi, którą chcesz ponownie zainstalować.
3. W menu operacji jednostki skalowania wybierz opcję **Aktualizuj**.
4. Na suwaku na liście rozwijanej opcji **Wybierz wersję** wybierz opcję **Określ wersję**.
5. W polu tekstowym w obszarze **Określ wersję** wpisz wersję wyświetlaną dla jednostki skalowania, wyświetlaną obok etykiety **Bieżąca wersja**.
6. Kliknij przycisk **Aktualizuj**.

Nie musisz wybierać **Uaktualnij rozszerzenia**, nawet jeśli wcześniej zastosowałeś rozszerzenia, ponieważ podczas aktualizacji jednostki skalowania automatycznie wybierany jest ostatni pakiet rozszerzeń zastosowany do jednostki.

Jeśli istnieje wiele jednostek skalowania, należy wykonać operację powyżej dla każdej z nich. W razie potrzeby te operacje można wykonywać równolegle.

## <a name="deploy-additional-commerce-scale-units-optional"></a>Wdrażanie dodatkowych Commerce Scale Unit (opcjonalne)

Po zainicjowaniu Commerce Scale Unit można wdrożyć samodzielnie drugą jednostkę, jeśli upoważnia do tego licencja. Aby wdrożyć więcej niż dwie jednostki skalowania, musisz utworzyć żądanie pomocy technicznej. W żądaniu pomocy technicznej należy wybrać żądaną liczbę Commerce Scale Unit, nazwę środowiska i żądane regiony. Aby uzyskać więcej informacji o licencjach, przejdź na [Przewodnik licencjonowania systemu Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409). 

Dla każdej kolejnej Commerce Scale Unit, którą wdrożysz, zalecamy utworzenie osobnej grupy baz danych kanałów, wykonując poniższe kroki.

1. W centrali rozwiązania Commerce przejdź do opcji **Retail i Commerce > Retail Headquarters > Ustawienia Transferu danych w sieci sprzedaży > Commerce Scheduler > Grupa baz danych kanałów**.
2. Utwórz nową grupę baz danych kanału.
3. Przejdź do **Retail i commerce > Retail Headquarters > Konfiguracja transferu danych w sieci sprzedaży > Baza danych kanału** i wybierz bazę danych kanałów, która odpowiada nowo utworzonej jednostce Commerce Scale Unit.
4. Wybierz pozycję **Edytuj** i wybierz nową grupę baz danych kanału.
5. Wybierz opcję **Zapisz**.
6. Wybierz opcję **Uruchom pełną synchronizację danych** dla wybranej bazy danych kanału.

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>Dodatkowe uwagi dotyczące inicjowania składników kanału Commerce hostowanych w chmurze w istniejącym środowisku

Jeśli już korzystasz z komponentów Commerce Channel w środowisku cloud-hosted, inicjalizacja Commerce Scale Unit pomoże zredukować przestoje podczas aktualizacji tych komponentów. Przed uruchomieniem Commerce Scale Unit wymagane jest dodatkowe planowanie.

Kiedy zainicjalizujesz swoją pierwszą Commerce Scale Unit w środowisku, które korzysta z komponentów kanałów Commerce w chmurze, proces inicjalizacji przeniesie Twoje kanały powiązane z komponentami kanałów w chmurze do pierwszej jednostki skalującej. Kanały związane z jednostkami Store Scale pozostają nienaruszone.

Proces migracji jest przejrzysty dla kanałów. Po rozpoczęciu inicjalizacji jednostki wagi automatycznie wykonywane są następujące operacje:

1. Zostanie utworzona i powiązana ze środowiskiem nowa jednostka Commerce Scale Unit.
2. Commerce Scale Unit zostanie zarejestrowana w centrali jako dostępna Baza Kanałów.
3. Wszystkie kanały zmapowane do bazy kanałów **Domyślna** w centrali zostaną zaktualizowane, aby zmapować je do nowej jednostki Commerce Scale Unit.
4. Zostanie wykonana pełna synchronizacja danych Commerce Data Exchange (CDX), aby przechować dane kanału do nowej jednostki skalowania.

**Planowanie i testowanie inicjowania jednostki skalowania Commerce** Ogólną zasadą jest, że podczas inicjalizacji Commerce Scale Unit musisz zaplanować pięciogodzinne okno przestoju dla operacji sklepowych oraz wszystkich operacji w kanale e-commerce, które używają serwera Retail lub punktu sprzedaży w chmurze.

1. Wykonaj odświeżenie bazy danych ze środowiska produkcyjnego do środowiska piaskownicy UAT. 
2. Zainicjuj Commerce Scale Unit w środowisku piaskownicy UAT. 
3. Zwróć uwagę na czas, jaki upływa do zakończenia inicjalizacji Commerce Scale Unit. Będzie to porównywalne z czasem, jaki ta operacja zajmuje w twoim środowisku produkcyjnym, podczas którego operacje sklepowe i e-commerce będą niedostępne.

Przed inicjalizacją modułu Commerce Scale Unit musisz wykonać następujące dodatkowe czynności.

- **Zamknij wszystkie zmiany w POS** – po migracji użytkownicy POS nie będą mogli zamknąć żadnych zmian, które były aktywne podczas procesu migracji.
- **Sprawdź, czy wszystkie zadania P-jobs zostały zakończone pomyślnie** – Zaleca się, by zadania P-jobs synchronizujące oczekujące transakcje zostały zakończone przed inicjalizacją CSU.
- **Wyloguj się ze wszystkich urządzeń w programie POS** – operacje w programie POS nie są obsługiwane podczas migracji.
- **Odwołaj i unieważnij wszystkie zawieszone transakcje w programie POS** – zawieszone transakcje nie są zachowywane w ramach inicjowania.

> [!IMPORTANT]
> W ramach inicjowania jednostki skalowania Commerce Scale Unit wcześniej zawieszone transakcje zostaną utracone i nie można ich odwołać. 

Oto, co dzieje się w okresie inicjowania:

- Hostowane w chmurze kanały handlowe Commerce nie będą działać, chyba że włączysz funkcję trybu offline programu POS.
- Urządzenia w aplikacji POS z włączonymi funkcjami offline będą mieć zredukowaną funkcjonalność.
- Klienty e-Commerce zależne od usługi serwera Retail zostaną przerwane.
- Nie będzie to dotyczyć kanałów hostowanych w jednostkach Commerce Scale Unit (obsługiwanych samodzielnie).
- Nie ma to wpływu na funkcjonalność centrali.

Oto, co dzieje się po zakończeniu inicjalizacji:

- Stan aktywacji urządzeń we wszystkich aktywowanych urządzeniach POS jest zachowany, co oznacza, że nie trzeba będzie ich ponownie aktywować.
- Samodzielne instancje stacji sprzętowych będą nadal działać.
- Raporty po stronie kanałów POS zostaną zresetowane i nie będą pokazywały danych sprzed inicjalizacji.
- Operacja Pokaż dziennik również zostanie zresetowana i nie będzie pokazywać danych sprzed inicjalizacji.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
