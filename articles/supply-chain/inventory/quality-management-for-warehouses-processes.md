---
title: Zarządzanie jakością dla procesów magazynowych
description: Ten temat zawiera informacje o procesie zarządzania jakością dla funkcji procesów magazynu. Ta funkcja rozszerza możliwości zarządzania jakością i umożliwia użytkownikom integrowanie kontroli przez pobieranie próbek towarów z procesem przyjmowania do magazynu przy użyciu zaawansowanego zarządzania magazynem.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-04-02
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: a8a7ac8266c14791137f9eda51b5abb5a59e5961
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679059"
---
# <a name="quality-management-for-warehouse-processes"></a>Zarządzanie jakością dla procesów magazynowych

[!include [banner](../includes/banner.md)]

Funkcja _Zarządzanie jakością dla procesów magazynowych_ umożliwia użytkownikom integrowanie kontroli przez pobieranie próbek towarów z procesem przyjmowania do magazynu przy użyciu zaawansowanego zarządzania magazynem. Pracę magazynową można automatycznie wygenerować, aby przenieść zapasy do lokalizacji kontroli jakości na podstawie wartości procentowej lub stałej ilości albo na podstawie każdego *n*-tego numeru identyfikacyjnego. Po zakończeniu zlecenia kontroli jakości można automatycznie wygenerować pracę, aby przenieść zapasy do kolejnej lokalizacji w procesie, w zależności od wyników kontroli jakości.

Funkcja _Zarządzanie jakością dla procesów magazynowych_ rozszerza możliwości podstawowej funkcji zarządzania jakością. Zapewnia ona możliwość tworzenia zleceń kontroli jakości dla zapasów wysyłanych do lokalizacji kontroli jakości, mimo że zlecenia kontroli jakości nie zawsze są wymagane. Dzięki temu można uzyskać uproszczony proces kontroli jakości oparty na pracy magazynowej.

## <a name="turn-on-the-quality-management-for-warehouse-processes-feature"></a>Włączanie funkcji Zarządzanie jakością dla procesów magazynowych

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Zarządzanie jakością dla procesów magazynowych*

## <a name="key-benefits"></a>Główne korzyści

Funkcja _Zarządzanie jakością dla procesów magazynowych_ automatycznie generuje pracę jako część procesu przyjęcia, aby przenieść ilość zapasów wymaganą do kontroli jakości do lokalizacji kontroli jakości. Jeśli otrzymana ilość przekracza ilość wymaganą do kontroli jakości (zgodnie z konfiguracją wyrywkowej kontroli towaru), ilość nadwyżki jest przenoszona do lokalizacji rozładunkowej zdefiniowanej w ustawieniach dyrektywy lokalizacji. Po sprawdzeniu zlecenia kontroli jakości praca jest automatycznie generowana w celu przeniesienia ilości dla zlecenia kontroli jakości do nowej lokalizacji przychodzącej lub zwrotu na podstawie wyniku weryfikacji i konfiguracji dyrektywy lokalizacji. Automatyczne generowanie pracy, która ma tylko ilość, która musi zostać przeniesiona do i z kontroli jakości, zapewnia zintegrowane doświadczenie procesu.

> [!NOTE]
> Jeśli funkcja _Zarządzanie jakością dla procesów magazynowych_ jest włączona, nadal można korzystać z procesu ręcznego. W procesie ręcznym przesunięcia zapasów i przesunięć według szablonów umożliwiają pracownikowi magazynowego uruchomienie tworzenia pracy magazynowej w celu przeniesienia zapasów z lokalizacji kontroli jakości do nowej lokalizacji. Istnieje również możliwość skonfigurowania dyrektywy lokalizacji rozładunkowej, która przenosi zapasy w całości z lokalizacji przyjęcia do lokalizacji kontroli jakości bez uwzględnienia konfiguracji kontroli wyrywkowej towarów.

## <a name="quality-management-and-the-quality-management-for-warehouse-processes-feature"></a>Zarządzanie jakością i funkcja Zarządzania jakością dla procesów magazynowych

Gdy funkcja _Zarządzania jakością dla procesów magazynowych_ jest włączona, zmienia się konfiguracja jednostek kluczowych zarządzania magazynem i zarządzania jakością. Poniższa ilustracja przedstawia informacje o jednostkach, które włączają zlecenia kontroli jakości dla procesów magazynowych. Tekst w nawiasach wskazuje sugerowane działania, gdy zastosowano funkcję zarządzania jakością przed włączeniem funkcji _Zarządzania jakością dla procesów zarządzania magazynem_.

![Jednostki zarządzania jakością.](media/quality-management-entity-diagram.png "Jednostki zarządzania jakością")

## <a name="enablers-the-quality-item-sampling-and-quality-order-work-order-types"></a>Czynniki: typy zlecań pracy Wyrywkowej kontroli jakości towaru i Zlecenie kotroli jakości

Funkcja _Zarządzania jakością dla procesów magazynowych_ wprowadza dwa typy zleceń pracy, które umożliwiają proces tworzenia pracy:

- **Wyrywkowa kontrola jakości towaru** — ten typ zlecenia jest używany do tworzenia pracy, która przenosi zarejestrowane zapasy do kontroli jakości.
- **Zlecenie kontroli jakości** — ten typ zlecenia służy do tworzenia pracy, która przenosi zapasy z kontroli jakości do nowej lokalizacji na podstawie konfiguracji dyrektywy lokalizacji.

### <a name="work-classes-location-directives-and-work-templates"></a>Klasy robocze, dyrektywy lokalizacji i szablony pracy

Typy zleceń pracy _Wyrywkowa kontrola jakości towaru_ i _Zlecenie kontroli jakości_ są zużywane według dyrektyw lokalizacji, klas roboczych i szablonów pracy.

Przed automatycznym wygenerowaniem pracy magazynowej w celu przeniesienia zapasów do kontroli jakości należy wykonać poniższe kroki, aby skonfigurować system.

1. Stwórzoddzielne klasy robocze dla typów zleceń pracy _Wyrywkowa kontrola jakości towaru_ i _Zlecenie kontroli jakości_. W ten sposób można zapewnić, że odpowiednia praca może być generowana automatycznie na podstawie dwóch typów zlecenia pracy, a następnie można uruchomić tę pracę za pomocą aplikacji Warehouse Management.
1. Ustaw szablony pracy dla każdego typu zlecenia:

    - Skonfiguruj szablon pracy, w którym jest używany typ zlecenia pracy _Wyrywkowa kontrola jakości towaru_, w celu automatycznego przeniesienia zarejestrowanego zapasu do lokalizacji kontroli jakości.
    - Skonfiguruj szablon pracy, w którym jest używany typ zlecenia pracy _Wyrywkowa kontrola jakości towaru jakości towaru_, w celu automatycznego przeniesienia zarejestrowanego zapasu do lokalizacji kontroli jakości.

1. Dla każdego typu zlecenia pracy należy skonfigurować dyrektywy lokalizacji, które stosują poprawne lokalizacje kontroli jakości, do których należy przenieść zapasy. Po zakończeniu kontroli jakości dyrektywa lokalizacji dla typu zlecenia pracy _Zlecenie kontroli jakości_ gwarantuje, że zostanie wybrana nowa lokalizacja docelowa, aby można było przenieść zapasy z lokalizacji kontroli jakości.
1. Skonfiguruj odpowiednie elementy menu urządzeń przenośnych w celu obsługi przepływu odebranych zapasów do lokalizacji kontroli jakości oraz przenoszenia zapasów, które przechodzą kontrolę jakości z wynikiem pozytywnym lub negatywnym z lokalizacji kontroli jakości do nowej lokalizacji.

Aby zapoznać się z przykładem krok po kroku, który pokazuje, jak ukończyć tę instalację, zajrzyj do [przykładowego scenariusza](#example-scenario) na końcu tego tematu.

## <a name="enable-a-warehouse-for-quality-management"></a>Włącz magazyn do zarządzania jakością

Aby można było zastosować funkcję _Zarządzanie jakością dla procesów magazynowych_ dla określonego magazynu, należy wykonać poniższe kroki, aby udostępnić tę funkcję dla danego magazynu.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Magazyny**.
1. Wybierz magazyn, aby włączyć zarządzanie jakością.
1. W skróconej karcie **Magazyn** należy w ustawieniu opcji **Włącz zlecenie kontroli jakości dla procesów magazynowych** wybrać wartość _Tak_. (Należy pamiętać, że ta opcja może być ustawiona jako _Tak_ tylko dla magazynów korzystających z procesów zarządzania magazynem.)

Jeśli opcja **Włącz zlecenie kontroli jakości dla procesów magazynowych** jest ustawiona na wartość _Tak_, ustawienie skojarzenia jakości określa, czy funkcja _Zarządzania jakością dla procesów magazynowych_ jest rzeczywiście stosowana dla wybranego magazynu. Można zmieniać ustawienie opcji na wartość _Nie_ w każdej chwili. W takim przypadku funkcja nie będzie już stosowana do magazynu, niezależnie od konfiguracji skojarzenia jakości.

## <a name="quality-control"></a>Kontrola jakości

Funkcja _Zarządzania jakością dla procesów magazynowych_ steruje kilkoma kluczowymi ustawieniami skojarzeń jakości i wyrywkową kontrolą towaru.

### <a name="quality-associations"></a>Powiązania jakości

Ponadto poszczególne [rekordy skojarzenia jakości](enable-quality-management.md) określają serie testów, akceptowany poziom jakości (AQL) i plan pobierania próbek dotyczące zleceń kontroli jakości, które są generowane. Aby skonfigurować rekord skojarzenia jakości, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Skojarzenia jakości**.
1. Utwórz lub wybierz wpis skojarzenia jakości dla pozycji lub grupy, z którą pracujesz, lub dla wszystkich towarów.
1. Na skróconej karcie **Warunki** należy w polu **Odpowiedni typ magazynu** określić jedną z następujących wartości:

    - **Tylko zarządzanie jakością dla procesów magazynowych** — umożliwia aktywowanie funkcji _Zarządzania jakością dla procesów magazynowych_. Tę wartość można wybrać tylko w przypadku, gdy typem odwołania jest *Zakup* lub *Produkcja*.
    - **Wszystko** – Wyłączanie funkcji _Zarządzanie jakością dla procesów magazynowych_. Tę wartość należy wybrać dla wszystkich typów odwołań z wyjątkiem opcji *Zakup* i *Produkcja*.

> [!NOTE]
> Funkcja _Zarządzania jakością dla procesów magazynowych_ działa tylko wtedy, gdy towar w wierszu dokumentu źródłowego korzysta z zaawansowanych procesów zarządzania magazynem, a opcja **Włącz zlecenie kontroli jakości dla procesów magazynowych** jest ustawiona na wartość _Tak_ dla magazynu w wierszu dokumentu źródłowego.

Po zarejestrowaniu każdego towaru (lub zgłoszenia go jako gotowy) system określa, które skojarzenia jakości mają być stosowane.

Jeśli funkcja _Zarządzania jakością dla procesów magazynowych_ jest włączona, odpowiedni typ magazynu jest wstawiany logicznie do czwartej grupy wyszukiwania w hierarchii wyszukiwania skojarzeń jakości. Poniższa tabela przedstawia logiczną reprezentację hierarchii wyszukiwania.

| Grupa wyszukiwania | opis |
|---|---|
| Grupa 1 | Dla każdego skojarzenia jakości sprawdź **Typ odwołania**, **Typ zdarzenia** i wartości **Zgodności wykonania** z towarem. Jeśli istnieje odpowiednik w wierszu dokumentu źródłowego, przejdź do grupy 2. |
| Grupa 2 | Dla każdego skojarzenia jakości należy sprawdzić wartość **Kod towaru** (_Tabela_, _Grupa_ lub _Wszystkie_) w odniesieniu do towaru. _Tabela_ jest bardziej szczegółowa niż _Grupa_, a _Grupa_ jest bardziej szczegółowa niż _Wszystkie_. Jeśli istnieje zgodność z _Tabelą_ (określonym towarem), należy przejść do grupy 3. Jeśli nie ma dopasowania dla _Tabeli_, wyszukaj dopasowanie dla _Grupy_. Jeśli nie ma dopasowania dla _Grupy_, ma zastosowanie opcja _Wszystkie_. Jeśli istnieje dopasowanie, przejdź do grupy 3. |
| Grupa 3 | Dla każdego skojarzenia jakości sprawdź **Kod konta** i wartości **Kod zasobu** w odniesieniu do towaru. Stosowana logika przypomina logikę zastosowana do wartości **Kodu towaru**. |
| Grupa 4 | Dla każdego skojarzenia jakości należy sprawdzić wartość **Odpowiedni typ magazynu** (_Tylko zarządzanie jakością dla procesów magazynowych_ lub _Wszystkie_) dla danego towaru. Jeśli opcja **Włącz zlecenie kontroli jakości dla procesów magazynowych** jest ustawiona na wartość _Tak_ dla magazynu w dokumencie źródłowym, a towar w wierszu dokumentu źródłowego jest ustawiany na _Użyj procesów zarządzania magazynami_, oba skojarzenia, w których istnieje zgodność z _Tylko zarządzanie jakością dla procesów magazynowych,_ oraz skojarzenia, w których istnieje zgodność dla _Wszystkich_, będą miały zastosowanie, jeśli oba istnieją. Jeśli funkcja **Włącz zlecenie kontroli jakości dla procesów magazynowych** jest ustawiona na wartość _Nie_ dla magazynu w dokumencie źródłowym i towar w wierszu dokumentu źródłowego jest ustawiony na opcję _Użyj procesów zarządzania magazynami_, tylko zarządzanie jakością będzie miało zastosowanie. |

Na przykład zdefiniowano magazyn, w którym dla opcji **Włącz zlecenie kontroli jakości dla procesów magazynowych** jest ustawiona wartość _Tak_, a istnieją dwa skojarzenia jakości zdefiniowane dla typu odwołania do *Zakupu* : jeden dla wszystkich towarów, a drugi dla typu zdarzenia *Rejestracji*. Jedyną różnicą między dwoma skojarzeniami jakości jest wartość **Odpowiedni typ magazynu** : jest ona ustawiana _Wszystkie_ dla jednego skojarzenia jakości i _Tylko zarządzanie jakością dla procesów magazynowych_ dla drugiego. W takim przypadku obydwa skojarzenia jakości są równie określone i oba będą miały zastosowanie.

Wartość pola **Grupa testowa** dla skojarzeń jakości również jest czynnikiem. To pole określa procedurę testową, która musi zostać zastosowana. Jeśli wartość **Grupa testowa** jest taka sama dla obu skojarzeń, zostanie utworzone tylko jedno zlecenie kontroli jakości, dla skojarzenia jakości, w którym wartość **Odpowiedni typ magazynu** wynosi _Tylko zarządzanie jakością dla procesów magazynowych_ dla drugiego. Jeśli wartość **Grupy testowej** nie jest taka sama dla obu skojarzeń, zostaną utworzone dwa zlecenia kontroli jakości. Pierwsze zlecenie kontroli jakości zostanie utworzone dla skojarzenia jakości, w którym wartość **Odpowiedni typ magazynu** wynosi _Tylko zarządzanie jakością dla procesów magazynowych_. Drugie zlecenie kontroli jakości zostanie utworzone dla skojarzenia jakości, w którym wartość **Odpowiedni typ magazynu** wynosi _Wszystkie_.

> [!NOTE]
> Wartość _Tylko zarządzanie jakością dla procesów magazynowych_ jest traktowana jako bardziej szczegółowa niż _Wszystkie_, gdy kryteria dla skojarzeń jakości dla grup 1 i 2 są takie same, a grupa testowa jest taka sama. Dwa zlecenia kontroli jakości zostaną utworzone tylko wtedy, gdy grupy testowe są różne.

#### <a name="reference-types"></a>Typy odwołań

Jeśli wartość **Typ odwołania** to _Zakup_, a wartość **Odpowiedni typ magazynu** to _Tylko zarządzanie jakością dla procesów magazynowych_, pole **Typ zdarzenia** naskróconej karcie **Proces** musi mieć wartość _Rejestracja_. _Rejestracja_ jest jedynym obsługiwanym typem zdarzenia dla typu odwołania _Zakup_ podczas korzystania z funkcji _Zarządzanie jakością dla procesów magazynowych_.

#### <a name="quality-processing-policy"></a>Zasady przetwarzania kontroli jakości

Funkcja _Zarządzania jakością dla procesów magazynowych_ umożliwia tworzenie pracy tylko na podstawie wyrywkowej kontroli towarów. Dlatego umożliwia proces uproszczony. Tworzona ilość zapasów zależy od wyrywkowej kontroli towarów skojarzonej z skojarzeniem jakości. Jeśli jest używany proces uproszczony, po wprowadzeniu przez pracownika ilości w lokalizacji kontroli jakości dział jakości może ręcznie utworzyć zlecenie kontroli jakości, jeśli jest wymagane zlecenie kontroli jakości.

Pole **Zasady przetwarzania jakości** na skróconej karcie **Przetwarzanie zlecenia kontroli jakości** określa, czy zlecenie kontroli jakości jest tworzone także podczas tworzenia pracy w celu przeniesienia towaru do lokalizacji kontroli jakości. W tym polu można skonfigurować _Stwórz zlecenie kontroli jakości_ lub _Stwórz tylko pracę_. Wartość domyślna to _Tworzenie zlecenia kontroli jakości_.

> [!NOTE]
> Niezależnie od tego, czy zlecenia kontroli jakości są tworzone ręcznie czy automatycznie, system automatycznie generuje pracę, aby przenieść towary z lokalizacji kontroli jakości, gdy zlecenie kontroli jakości jest oznaczone jako sprawdzone.

Tworzenie pracy zlecenia kontroli jakości nie jest związane z konfiguracją skojarzenia jakości. Jeśli istnieje szablon pracy, który ma wartość **Typ zlecenia pracy** wynoszącą *Zlecenie kontroli jakości* i jeśli dla tego szablonu pracy są spełnione kryteria kwerendy, sprawdzenie poprawności zlecenia kontroli jakości spowoduje wyzwolenie utworzenia pracy zlecenia kontroli jakości.

#### <a name="referenced-item-sampling"></a>Wyrywkowa kontrola jakości, której dotyczy odwołanie

Każde skojarzenie jakości musi odwoływać się do kontroli wyrywkowej towaru. Kontrola wyrywkowa towaru określa ilość, która zostanie wysłana w celu kontroli jakości. Można ją skonfigurować tak, aby dotyczyła tylko skojarzeń jakości, w których wartość **Odpowiedni typ magazynu** wynosi _Tylko zarządzanie jakością dla procesów magazynowych_. Jeśli wartość **Zakresu kontroli wyrywkowej towarów** dla kontroli wyrywkowej towaru jest _Ładunek_ lub _Wysyłka_, lub wartość **Specyfikacji ilości** to _Pełny numer identyfikacyjny_, można odwoływać się do tej kontroli tylko za pomocą skojarzeń jakości, w których wartość **Odpowiedni typ magazynu** wynosi _Tylko zarządzanie jakością dla procesów magazynowych_.

W przypadku zdefiniowania kontroli wyrywkowej towaru, w której jest używany odpowiedni typ magazynu _Tylko zarządzanie jakością dla procesów magazynowych_, podczas próby odwołania się do niej ze skojarzenia jakości, która nie korzysta z funkcji  _Zarządzanie jakością dla procesów magazynowych_, pojawi się błąd.

> [!NOTE]
> Kontrola wyrywkowa towarów korzystająca z pełnego blokowania nie jest obsługiwana w przypadku skojarzeń jakości, w których pole **Odpowiedni typ magazynu** jest ustawione na _Tylko zarządzanie jakością dla procesów magazynowych_.

### <a name="item-sampling"></a>Kontrola wyrywkowa pozycji

Kontrola wyrywkowa towarów określa częstotliwość wysyłania towarów w celu kontroli jakości. Funkcja _Zarządzanie jakością dla procesów magazynowych_ wprowadza pojęcie _Zakresu kontroli wyrywkowej towarów_. System używa zakresu próbkowania towaru podczas oceniania, czy i jak mają zostać utworzone zlecenia kontroli jakości i/lub praca wyrywkowej kontroli jakości towarów oraz praca zlecenia kontroli jakości.

Aby skonfigurować wyrywkową kontrolę jakości, przejdź do **Zarządzanie zapasami \> Konfiguracja \> Kontrola jakości \> Kontrola wyrywkowa towarów** i ustaw pole **Zakres próbkowania** na jedną z następujących wartości:

- **Zlecenia** – Wiersz dokumentu źródłowego będzie podstawą do oceny, czy i w jaki sposób tworzone są zlecenia kontroli jakości i/lub praca wyrywkowej kontroli jakości towarów oraz praca zlecenia kontroli jakości. Ta wartość jest wartością domyślną, a po jej wybraniu system działa w taki sam sposób, jak działa, gdy funkcja _Zarządzanie jakością dla procesów magazynowych_ nie jest włączona.
- **Ładunek** — Ładunki będą używane jako podstawa do szacowania, czy i w jaki sposób ma być tworzona zlecenie kontroli jakości i/lub praca. Ta wartość jest dostępna tylko wtedy, gdy jest włączona funkcja _Zarządzanie jakością dla procesów magazynowych_.
- **Wysyłka** — Wysyłki będą używane jako podstawa do szacowania, czy i w jaki sposób ma być tworzona zlecenie kontroli jakości i/lub praca. Ta wartość jest dostępna tylko wtedy, gdy jest włączona funkcja _Zarządzanie jakością dla procesów magazynowych_.

> [!NOTE]
> Jeśli w polu **Zakres kontroli wyrywkowej** jest ustawiona wartość *Ładunek* lub *Wysyłka*, zostaną użyte jednostki ładunku i wysyłki, jeśli są dostępne. Jeśli nie są dostępne, zostanie użyta jednostka zamówienia.

Funkcja _Zarządzanie jakością dla procesów magazynowych_ wprowadza również wartość *Pełny numer identyfikacyjny* dla pola **Specyfikacja ilości**. Ta wartość umożliwia tworzenie pracy zlecenia kontroli jakości i pracy wyrywkowej kontroli jakości towarów na podstawie numerów identyfikacyjnych. Po wybraniu tej wartości zostaną wykonane następujące zmiany:

- Opcja **Podział według towaru** i pole **Na n-ty numer identyfikacyjny** staną się dostępne na skróconej karcie **Proces**.
- Pole **Wartość** na skróconej karcie **Ilość kontroli wyrywkowej towarów** stanie się niedostępne.
- Opcje **Dla zaktualizowanej ilości**, **Lokalizacja** i **Numer identyfikacyjny** są ustawione na wartość *Tak* i nie można zmienić ustawień.

Opcja **Podział według towaru** określa, czy liczba numerów identyfikacyjnych jest oceniana dla każdego towaru, czy dla wszystkich towarów w zakresie kontroli wyrywkowej towarów. Warianty produktów są traktowane jako ten sam towar. Ta opcja określa również, czy liczba numerów identyfikacyjnych jest resetowana dla każdego towaru.

Wartość **Na n-ty numer identyfikacyjny** określa częstotliwość tworzenia zleceń kontroli jakości w odniesieniu do liczby zarejestrowanych towarów. Na przykład wartość *3* spowoduje wysłanie każdej trzeciej pozycji do kontroli jakości, począwszy od pierwszego towaru. Wartość musi być większa od 0 (zera).

Podczas gdy pracownicy odbierają towary za pomocą aplikacji Warehouse Management, system sprawdza, czy dla każdego towaru przychodzącego skonfigurowano skojarzenie jakości. W przypadku skonfigurowania skojarzenia jakości system używa rekordu kontroli wyrywkowej towaru skonfigurowanego dla tego skojarzenia jakości w celu określenia sposobu tworzenia zleceń kontroli jakości, pracy kontroli wyrywkowej towarów oraz pracy zamówienia zakupu.

> [!NOTE]
> Po zakończeniu rejestracji paragonu w kliencie sieci Web (przy użyciu małej strony rejestracji lub arkusza przyjęć towarów w wierszach zamówienia zakupu) nie będą tworzone prace dotyczące wyrywkowej kontroli towarów i zamówienia zakupu niezależnie od ustawień. W przypadku towarów, które pasują do skojarzenia jakości, wyrywkowa kontrola towarów, do których następuje odwołanie, zostanie użyta w celu sterowania tworzeniem tylko zleceń kontroli jakości.

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Przykłady automatycznego generowania zleceń kontroli jakości

Poniższe przykłady przedstawiają sposób, w jaki ustawienia skojarzenia jakości i skojarzonego towaru mają wpływ na generowanie zleceń kontroli jakości, jeśli dla pola **Odpowiedni typ magazynu** jest ustawiona wartość _Tylko zarządzanie jakością dla procesów magazynowych_.

Jeśli wartość **Specyfikacji ilości** wynosi _Pełny numer identyfikacyjny_, pole **Na n-ty numer identyfikacyjny** określa, dla których numerów identyfikacyjnych utworzono pracę wyrywkowej kontroli jakości towarów. Pierwszy numer identyfikacyjny zawsze przechodzi do kontroli jakości, a następnie wartość tego pola określa, że każdy *n-ty* numer identyfikacyjny po tym numerze powinien być również przenoszony.

Wartością **Typu odwołania** dla poniższych przykładów jest _Zakup_, a wartością **Typu zdarzenia** jest *Rejestracja*.

| Zakres kontroli wyrywkowej | Specyfikacja ilości | Dla zaktualizowanej ilości | Dla wymiaru magazynowania | Podział liczebności wg pozycji | Dla n-tego numeru identyfikacyjnego | Wynik |
|---|---|---|---|---|---|---|
| Zamówienie | Cały obiekt pod numerem identyfikacyjnym | Tak _(zablokowano/nie można edytować)_ | <p>Lokalizacja: Tak</p><p>Numer identyfikacyjny: Tak _(zablokowano/nie można edytować)_</p> | Nie | 3 | <p>**Ilość w wierszu zamówienia: 100 EA**</p><ol><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP1<p>Praca wyrywkowej kontroli jakości towarów dla 20 EA</p><p>Zlecenie kontroli jakości 1 dla 20 EA</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP2<p>Praca zamówienia zakupu dla 20 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP3<p>Praca zamówienia zakupu dla 20 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP4<p>Praca wyrywkowej kontroli jakości towarów dla 20 EA</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP5<p>Praca zamówienia zakupu dla 20 EA (odłożenie)</p></li></ol> |
| Zamówienie | Stała ilość = 1 | Tak | <p>Lokalizacja: Tak</p><p>Numer identyfikacyjny: Tak</p> | Nie | Nie dotyczy | <p>**Ilość w wierszu zamówienia: 100**</p><ol><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP1<p>Praca wyrywkowej kontroli jakości towaru dla 1 EA</p><p>Zlecenie kontroli jakości 1 dla 1 EA</p><p>Praca zamówienia zakupu dla 19 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP2<p>Praca wyrywkowej kontroli jakości towaru dla 1 EA</p><p>Zlecenie kontroli jakości 1 dla 1 EA</p><p>Praca zamówienia zakupu dla 19 (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP3<p>Praca wyrywkowej kontroli jakości towaru dla 1 EA</p><p>Zlecenie kontroli jakości 1 dla 1 EA</p><p>Praca zamówienia zakupu dla 19 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP4<p>Praca wyrywkowej kontroli jakości towaru dla 1 EA</p><p>Zlecenie kontroli jakości 1 dla 1 EA</p><p>Praca zamówienia zakupu dla 19 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 20 EA, LP5<p>Praca wyrywkowej kontroli jakości towaru dla 1 EA</p><p>Zlecenie kontroli jakości 1 dla 1 EA</p><p>Praca zamówienia zakupu dla 19 EA (odłożenie)</p></li></ol> |
| Zamówienie | Procent = 10 | Nie | <p>Lokalizacja: Nie</p><p>Numer identyfikacyjny: Nie</p> | Nie | Nie dotyczy | <p>**Ilość w wierszu zamówienia: 100 EA**</p><ol><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 50 EA, LP1<p>wyrywkowej kontroli jakości towaru dla 10 EA</p><p>Zlecenie kontroli jakości 1 dla 10 EA</p><p>Praca zamówienia zakupu dla 40 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 50 EA, LP2<p>Praca zamówienia zakupu dla 50 EA (odłożenie)</p></li></ol> |
| Obciążenie pracą | Procent = 5 | Tak _(zablokowano/nie można edytować)_ | <p>Lokalizacja: Nie</p><p>Numer identyfikacyjny: Nie</p> | Nie | Nie dotyczy | <p>**Ilość w wierszu zamówienia: 500 EA**</p><p>**Dwa ładunki: pierwsze obciążenie 200 EA, drugi ładunek 300 EA**</p><ol><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pierwszego ładunku na 100 EA<p>Praca wyrywkowej kontroli jakości towaru dla 5 EA</p><p>Zlecenie kontroli jakości 1 dla 5 EA</p><p>Praca zamówienia zakupu dla 95 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pierwszego ładunku na 100 EA<p>Praca wyrywkowej kontroli jakości towaru dla 5 EA</p><p>Zlecenie kontroli jakości 1 dla 5 EA</p><p>Praca zamówienia zakupu dla 95 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla drugiego ładunku na 300 EA<p>Praca wyrywkowej kontroli jakości towaru dla 15 EA</p><p>Zlecenie kontroli jakości 1 dla 15 EA</p><p>Praca zamówienia zakupu dla 285 EA (odłożenie)</p></li></ol> |
| Kolejność | Procent = 10 | Tak | <p>Lokalizacja: Tak</p><p>Numer identyfikacyjny: Tak</p> | Nie | Nie dotyczy | <p>**Ilość w wierszu zamówienia: 100**</p><ol><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 50 EA, LP1<p>Praca wyrywkowej kontroli jakości towaru dla 5 EA</p><p>Zlecenie kontroli jakości 1 dla 5 EA</p><p>Praca zamówienia zakupu dla 45 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 50 EA, LP2<p>Praca wyrywkowej kontroli jakości towaru dla 5 EA</p><p>Zlecenie kontroli jakości 1 dla 5 EA</p><p>Praca zamówienia zakupu dla 45 (odłożenie)</p></li></ol> |
| Obciążenie pracą | Cały obiekt pod numerem identyfikacyjnym | Tak _(zablokowano/nie można edytować)_ | <p>Lokalizacja: Tak</p><p>Numer identyfikacyjny: Tak _(zablokowano/nie można edytować)_</p> | Nie | 3 | <p>**Dwa towary:**</p><ul><li>**Ilość w wierszu zamówienia dla pozycji A: 120 EA (4 palety)**</li><li>**Ilość w wierszu zamówienia dla pozycji B: 90 EA (3 palety)**</li></ul><p>**Jeden ładunek, dwa wiersze ładunku z każdym wierszem zamówienia**</p><ol><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP1<p>Praca wyrywkowej kontroli jakości towaru dla 30 EA</p><p>Zlecenie kontroli jakości 1 dla 30 EA</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP2<p>Praca zamówienia zakupu dla 30 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP3<p>Praca zamówienia zakupu dla 30 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP4<p>Praca wyrywkowej kontroli jakości towaru dla 30 EA</p><p>Zlecenie kontroli jakości 1 dla 30 EA</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru B, 30 EA, LP5<p>Praca zamówienia zakupu dla 30 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru B, 30 EA, LP6<p>Praca zamówienia zakupu dla 30 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP7<p>Praca wyrywkowej kontroli jakości towaru dla 30 EA</p><p>Zlecenie kontroli jakości 1 dla 30 EA</p></li></ol> |
| Obciążenie pracą | Cały obiekt pod numerem identyfikacyjnym | Tak _(zablokowano/nie można edytować)_ | <p>Lokalizacja: Tak</p><p>Numer identyfikacyjny: Tak _(zablokowano/nie można edytować)_</p> | Tak | 3 | <p>**Dwa towary:**</p><ul><li>**Ilość w wierszu zamówienia dla pozycji A: 120 EA (4 palety)**</li><li>**Ilość w wierszu zamówienia dla pozycji B: 90 EA (3 palety)**</li></ul><p>**Jeden ładunek, dwa wiersze ładunku z każdym wierszem zamówienia**</p><ol><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP1<p>Praca wyrywkowej kontroli jakości towaru dla 30 EA</p><p>Zlecenie kontroli jakości 1 dla 30 EA</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP2<p>Praca zamówienia zakupu dla 30 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP3<p>Praca zamówienia zakupu dla 30 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP4<p>Praca wyrywkowej kontroli jakości towaru dla 30 EA</p><p>Zlecenie kontroli jakości 1 dla 30 EA</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru B, 30 EA, LP5<p>Praca wyrywkowej kontroli jakości towaru dla 30 EA</p><p>Zlecenie kontroli jakości 1 dla 30 EA</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru B, 30 EA, LP6<p>Praca zamówienia zakupu dla 30 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla towaru A, 30 EA, LP7<p>Praca zamówienia zakupu dla 30 EA (odłożenie)</p></li></ol> |
| Obciążenie pracą | Procent = 10 | Tak _(zablokowano/nie można edytować)_ | <p>Lokalizacja: Nie</p><p>Numer identyfikacyjny: Nie</p> | Nie | Nie dotyczy | <p>**Ilość w wierszu zamówienia: 100 EA**</p><p>**Nie są tworzone żadne ładunki. Zakres zamówienia jest stosowany.**</p><ol><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 50 EA, LP1<p>Praca wyrywkowej kontroli jakości towaru dla 5 EA</p><p>Zlecenie kontroli jakości 1 dla 5 EA</p><p>Praca zamówienia zakupu dla 45 EA (odłożenie)</p></li><li>Rejestrowanie przyjęcia w aplikacji Warehouse Management dla pozycji A, 50 EA, LP2<p>Praca wyrywkowej kontroli jakości towaru dla 5 EA</p><p>Zlecenie kontroli jakości 1 dla 5 EA</p><p>Praca zamówienia zakupu dla 45 EA (odłożenie)</p></li></ol> |

Gdy pracownik sprawdza poprawność jednego z zleceń kontroli jakości, które zostały przedstawione w poprzedniej tabeli, system automatycznie generuje zadanie kontroli jakości w celu przeniesienia zapasów z lokalizacji kontroli jakości do lokalizacji określonej w dyrektywie lokalizacji dla typu zlecenia produkcyjnego dla _zlecenia kontroli jakości_. W zależności od wyników testu dla zlecenia kontroli jakości można skonfigurować dowolną lokalizację do tego celu, taką jak zwrot lub lokalizacja przechowywania. Aby zapoznać się z przykładem tej konfiguracji, należy zapoznać się z [przykładowym scenariuszem](#example-scenario) na końcu tego tematu.

Można ponownie otworzyć zlecenie kontroli jakości, które zostało już zweryfikowane, pod warunkiem, że praca zlecenia kontroli jakości związana z przenoszeniem zapasów z lokalizacji kontroli jakości nie ma wartości **Stanu pracy** wynoszącej *Zamknięty* lub *W toku*.

## <a name="process-insights-when-multiple-quality-associations-coexist"></a>Przetwarzaj szczegółowe dane, gdy współistnieje wiele skojarzeń jakości

Można zdefiniować więcej niż jedno skojarzenie jakości i zastosować je do tego samego wiersza dokumentu źródłowego, a pole **Odpowiedni typ magazynu** można skonfigurować zarządzanie _Tylko zarządzanie jakością dla procesów magazynowych_ dla niektórych z tych skojarzeń jakości i _Wszystkie_ dla innych skojarzeń.

W poniższym przykładzie wartością **Typu odwołania** jest _Zakup_.

1. Pierwsze skojarzenie jakości jest konfigurowane w następujący sposób:

    - **Odpowiedni typ magazynu:** *Tylko zarządzanie jakością dla procesów magazynowych*
    - **Kod pozycji:** *A0001*
    - **Kod konta:** *Wszystkie*
    - **Grupa testowa:** *Odgrodzona*
    - **Kontrola wyrywkowa towaru:** *5 szt*

1. Drugie skojarzenie jakości jest konfigurowane w następujący sposób:

    - **Odpowiedni typ magazynu:** *Wszystkie*
    - **Kod pozycji:** *Wszystko*
    - **Kod konta:** *Wszystkie*
    - **Grupa testowa:** *Odgrodzona*
    - **Kontrola wyrywkowa towaru:** *1 szt*

1. Trzecie skojarzenie jakości jest konfigurowane w następujący sposób:

    - **Odpowiedni typ magazynu:** *Tylko zarządzanie jakością dla procesów magazynowych*
    - **Kod pozycji:** *Wszystko*
    - **Kod konta:** *104*
    - **Grupa testowa:** *Opór*
    - **Kontrola wyrywkowa towaru:** *Co drugi numer identyfikacyjny* (to ustawienie oznacza, że w pierwszym, trzecim, piątym i tak dalej, z otrzymanych numerów identyfikacyjnych zostanie utworzone zlecenie kontroli jakości.)

1. Czwarte skojarzenie jakości jest konfigurowane w następujący sposób:

    - **Odpowiedni typ magazynu:** *Wszystkie*
    - **Kod pozycji:** *Wszystko*
    - **Kod konta:** *Wszystkie*
    - **Grupa testowa:** *Opór*
    - **Kontrola wyrywkowa towaru:** *5 szt*

1. Piąte skojarzenie jakości jest konfigurowane w następujący sposób:

    - **Odpowiedni typ magazynu:** *Wszystkie*
    - **Kod pozycji:** *Wszystko*
    - **Kod konta:** *Wszystkie*
    - **Grupa testowa:** *Stożek*
    - **Kontrola wyrywkowa towaru:** *10%*

Dla dostawcy 104 utworzono zamówienie zakupu dla ilości 10 pozycji A0001. Następnie wiersz zamówienia zakupu z ilością 10 jest rejestrowany jako przyjęty na jednym numerze identyfikacyjnym za pomocą aplikacji Warehouse Management. Oto wynik:

- Istnieje jedno zlecenie kontroli jakości od pierwszego skojarzenia jakości dla grupy testowej *Odgrodzonej*. Ilość wynosi 5. Nie ma zlecenia kontroli jakości na podstawie drugiego skojarzenia jakości, ponieważ kryteria pierwszego skojarzenia jakości są bardziej właściwe względem grupy testowej *Odgrodzonej*.
- Istnieje jedno zlecenie kontroli jakości dla trzeciego skojarzenia jakości dla grupy testowej *Opór*. Ilość wynosi 10. Nie ma zlecenia kontroli jakości na podstawie czwartego skojarzenia jakości, ponieważ kryteria pierwszego skojarzenia jakości są bardziej właściwe względem grupy testowej *Opór*.
- Istnieje jedno zlecenie kontroli jakości dla piątego skojarzenia jakości dla grupy testowej *Stożek*. Ilość wynosi 1.

W związku z tworzeniem jednego zlecenia kontroli jakości dla każdego z trzech skojarzeń jakości jest również tworzona praca wyrywkowej kontroli jakości towaru. Zarejestrowana ilość wynosi tylko 10. Jednak ze względu na ustawienia kontroli wyrywkowej, suma ilości zlecenia kontroli jakości, które zostały utworzone dla odpowiedniego typu magazynu *Tylko zarządzanie jakością dla procesów magazynowych* wartości 16, co przekracza ilość fizyczną zarejestrowaną jako 10. Dlatego nie można utworzyć pracy dla pełnej ilości zlecenia kontroli jakości (16), ponieważ tylko 10 jest fizycznie dostępnych do przeniesienia do lokalizacji kontroli jakości. Priorytet używany do tworzenia pracy wyrywkowej kontroli jakości towaru jest zgodny z kolejnością tworzenia zlecenia kontroli jakości:

- **Pierwsze zlecenie kontroli jakości (ilość = 5):** Utworzono pracę wyrywkowej kontroli jakości towaru dla 5. Ilość 5 (10 – 5) pozostanie teraz dla kolejnych operacji tworzenia pracy wyrywkowej kontroli jakości towaru.
- **Drugie zlecenie kontroli jakości (ilość = 10):** Utworzono pracę wyrywkowej kontroli jakości towaru dla 5. Ilość 0 (zero) pozostanie teraz dla kolejnych operacji tworzenia pracy wyrywkowej kontroli jakości towaru.
- **Trzecie zlecenie kontroli jakości (ilość = 1):** Nie utworzono żadnej pracy wyrywkowej kontroli jakości towaru.

W ramach procesu tworzenia zleceń kontroli jakości jest tworzona blokada zapasów o ilości 10. Do tego blokowania zapasów odwołują się wszystkie trzy zlecenia kontroli jakości. Suma ilości w zleceniu kontroli jakości wynosi 16.

Po sprawdzeniu poprawności zleceń kontroli jakości system próbuje utworzyć pracę zlecenia kontroli jakości dla każdego sprawdzonego zlecenia kontroli jakości. Ponieważ suma ilości w zleceniu kontroli jakości przekracza ilość, która jest rzeczywiście zablokowana i w związku z tym jest dostępna do utworzenia pracy, nie można utworzyć pracy zlecenia kontroli jakości w odniesieniu do pełnych ilości zlecenia kontroli jakości, jak to pokazano poniżej. (W tym przykładzie jest kontynuowany poprzedni przykład.)

1. **Sprawdź poprawność drugiego tworzonego zlecenia kontroli jakości (ilość = 10). Dla ilości 4 utworzono pracę zlecenia kontroli jakości.**

    Tworzenie pracy zlecenia kontroli jakości jest wyzwalane przez zmianę w ilości blokującej zapasy. Ponieważ suma ilości zlecenia kontroli jakości wynosi 16, potwierdzenie ilości 10 spowoduje, że pozostałe ilości zlecenia kontroli jakości zostaną potwierdzone jako równe 6. Ilość blokowania zapasów jest zmniejszona z 10 do 6. Zmniejszona ilość 4 jest przydzielona do tworzenia pracy zlecenia kontroli jakości.

2. **Sprawdź poprawność pierwszego tworzonego zlecenia kontroli jakości (ilość = 5). Dla ilości 5 utworzono pracę zlecenia kontroli jakości.**

    Tworzenie pracy zlecenia kontroli jakości jest wyzwalane przez zmianę w ilości blokującej zapasy. Ponieważ suma ilości zlecenia kontroli jakości wynosi 6, potwierdzenie ilości 5 spowoduje, że pozostałe ilości zlecenia kontroli jakości zostaną potwierdzone jako równe 1. Ilość blokowania zapasów jest zmniejszona z 6 do 1. Zmniejszona ilość 5 jest przydzielona do tworzenia pracy zlecenia kontroli jakości.

3. **Sprawdź poprawność trzeciego tworzonego zlecenia kontroli jakości (ilość = 1). Dla ilości 1 utworzono pracę zlecenia kontroli jakości.**

    Tworzenie pracy zlecenia kontroli jakości jest wyzwalane przez zmianę w ilości blokującej zapasy. Ponieważ suma ilości zlecenia kontroli jakości wynosi 1, potwierdzenie ilości 1 spowoduje, że pozostałe ilości zlecenia kontroli jakości zostaną potwierdzone jako równe 0 (zero). Blokowanie zapasów jest usuwane (oznacza to, że ilość blokowania zapasów jest zmniejszana z 1 do 0). Zmniejszona ilość 1 jest przydzielona do tworzenia pracy zlecenia kontroli jakości.

> [!NOTE]
> Tworzenie pracy zlecenia kontroli jakości zależy od ilości blokowania zapasów, do której odwołuje się jedno lub więcej zleceń kontroli jakości. Jeśli suma ilości zlecenia kontroli jakości przekracza ilość, do której odwołuje się blokada zapasów, kolejność, w jakiej sprawdzane są zlecenia kontroli jakości, określa sposób tworzenia pracy zlecenia kontroli jakości.

## <a name="canceling-quality-item-sampling-work"></a>Anulowanie pracy wyrywkowej kontroli jakości towaru

Można anulować pracę utworzoną na potrzeby wyrywkowej kontroli jakości towaru.. Aby określić, co ma się pojawiać po anulowaniu tej pracy, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na karcie **Ogólne**, w skróconej karcie **Praca**, ustaw opcję **Cofnij rejestrację paragonu podczas anulowania pracy** na jedną z następujących wartości:

    - **Tak** — gdy praca związana z wyrywkową kontrolą jakości jest anulowana, skojarzone zlecenie kontroli jakości jest usuwane, a zapasy są wyrejestrowane.
    - **Nie** — gdy praca związana z wyrywkową kontrolą jakości jest anulowana, skojarzone zlecenie kontroli jakości nie jest usuwane, a zapasy nie są wyrejestrowane.

## <a name="cross-docking"></a>Przeładunek kompletacyjny

Można skonfigurować ustawienia skojarzenia jakości, które będą tworzyły pracę wyrywkowej kontroli jakości towaru. Jednak w przypadku, gdy przeładunek kompletacyjny istnieje równolegle z powiązaniem jakości, które tworzy pracę wyrywkowej kontroli jakości towaru, jeśli istnieje tylko wystarczająca ilość, aby można było obsłużyć przeładunek kompletacyjny, zostanie utworzona tylko praca wyrywkowej kontroli towaru. W przypadkach, w których opcja **Włącz zlecenie kontroli jakości dla procesów magazynowych** ma wartość _Tak_ dla magazynu odbierającego , a pole **Odpowiedni typ magazynu** jest ustawione na _Tylko zarządzanie jakością dla procesów magazynowych_ dla skojarzenia jakości, utworzenie pracy wyrywkowej kontroli jakości towaru ma pierwszeństwo przed tworzeniem pracy przeładuneku kompletacyjnego. Jeśli ilość przekracza zapotrzebowanie na przeładunek komplementarny, system nadal tworzy tylko pracę wyrywkowej kontroli jakości towaru.

## <a name="destructive-testing"></a>Testy destrukcyjne

Można zdefiniować grupę testową, która przeprowadza testowanie destrukcyjne. W przypadku testu destrukcyjnego założenie jest takie, że niezależnie od wyniku testu, ilość testowanego towaru zostanie zniszczona jako część testu. Sposób, w jaki funkcja _Zarządzania jakością dla procesów magazynowych_ obsługuje testy destrukcyjne, jest podobna do sposobu, w jaki system zarządzania jakością obsługuje je, gdy funkcja nie jest włączona. Aby można było sprawdzić poprawność zlecenia kontroli jakości, kontroler jakości musi określać lokalizację odbioru dla ilości, która została zniszczona. Odbiór można rejestrować na stronie zlecenie kontroli jakości, wybierając pozycję **Zasoby \> Odbiór** w okienku akcji. Po zarejestrowaniu pobrania ilości zlecenia kontroli jakości można zakończyć weryfikację.

## <a name="example-scenario"></a>Przykładowy scenariusz

### <a name="prepare-the-scenario"></a>Przygotuj scenariusz

Aby pracować w tym scenariuszu, należy przygotować system w następujący sposób:

- Upewnij się, że dane demonstracyjne są zainstalowane w systemie i wybierz firmę **USMF**.
- Włącz funkcję _Zarządzanie jakością dla procesów magazynowych_ w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Skonfiguruj magazyn 51 do korzystania z funkcji _Zarządzanie jakością dla procesów magazynowych_, wykonując następujące kroki:

    1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Magazyny**.
    1. Wybierz magazyn 51.
    1. W skróconej karcie **Magazyn** należy w ustawieniu opcji **Włącz zlecenie kontroli jakości dla procesów magazynowych** wybrać wartość *Tak*.

### <a name="quality-in-setup--move-to-the-quality-control-location"></a>Konfiguracja jakości wejściowej — przejście do lokalizacji kontroli jakości

Należy teraz przygotować konfigurację podstawową, która umożliwi systemowi obsługę funkcji _Zarządzanie jakością dla procesów magazynowych_ w magazynie 51. (Dane demonstracyjne określają lokalizację zarządzania jakością o nazwie *QMS*. W tym scenariuszu ta lokalizacja jest przywoływana kilka razy.) Zostaną przygotowane następujące elementy, opisane w podsekcjach tej sekcji:

- Klasa robocza
- Szablon pracy
- Dyrektywa lokalizacji
- Kontrola wyrywkowa pozycji
- Skojarzenie jakości
- Elementy menu urządzenia przenośnego

#### <a name="work-class-for-quality-in"></a>Klasa robocza dla jakości wejściowej

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.
1. Utwórz klasę roboczą i określ następujące wartości:

    - **Identyfikator klasy roboczej:** _QualityIn_
    - **Opis:** _Wyrywkowa kontrola jakości towaru_
    - **Typ zlecenia pracy:** _Wyrywkowa kontrola jakości towaru_

#### <a name="work-template"></a>Szablon pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. W polu **Typ zlecenia pracy** ustaw wartość _Wyrywkowa kontrola jakości towaru_.
1. Utwórz szablon i określ następujące wartości:

    - **Szablon pracy:** _51 Jakość_
    - **Opis szablonu pracy:** _51 Jakość_

1. Dodaj wiersz do szablonu pracy i określ następujące wartości:

    - **Typ pracy:** _Pobranie_
    - **Identyfikator klasy roboczej:** _QualityIn_

1. Dodaj drugi wiersz do szablonu pracy i określ następujące wartości:

    - **Typ pracy:** _Odłożenie_
    - **Identyfikator klasy roboczej:** _QualityIn_

#### <a name="location-directive"></a>Dyrektywa lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W polu **Typ zlecenia pracy** ustaw wartość _Wyrywkowa kontrola jakości towaru_.
1. Utwórz dyrektywę lokalizacji i określ następujące wartości:

    - **Nazwa:** _51 do jakości_
    - **Typ pracy:** _Odłożenie_
    - **Oddział:** 5
    - **Magazyn:** _51_

1. Dodaj wiersz do dyrektywy lokalizacji i określ następujące wartości:

    - **Od ilości:** _1_
    - **Do ilości:** _1000000_

1. Utwórz akcję dyrektywe lokalizacji i określ następującą wartość:

    - **Nazwa:** _Jakość_

1. W przypadku nowej akcji dyrektywy lokalizacji wybierz opcję **Edytuj kwerendę** i określ rekord **Zakres** o następujących wartościach:

    - **Tabela:** *Lokalizacje*
    - **Pole:** _Identyfikator profilu lokalizacji_
    - **Kryteria QMS:** *QMS*

1. Wybierz **OK**, aby zapisać kwerendę i zapisać nową dyrektywę lokalizacji.

Następnie należy zmienić sekwencję dyrektyw dla istniejących lokalizacji zamówień zakupu dla magazynu 51. Dane demonstracyjne obejmują dwie dyrektywy lokalizacji, które mają wartość **Typ zlecenia pracy** wynoszącą _Zakup_: jedną o nazwie _51 QMS_, a drugą o nazwie _51 Zamówienia bezpośrednie_. Aby upewnić się, że funkcja *Zarządzanie jakością dla procesów magazynowych* jest stosowana dla magazynu 51, należy upewnić się, że dyrektywa dotycząca lokalizacji _51 QMS_ nie zostanie zastosowana. Jednak zamiast usuwania tej dyrektywy lokalizacji (ponieważ może ona być używana w przyszłości), wystarczy zmienić tę sekwencję.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W polu **Typ zlecenia pracy** zaznacz opcję _Zamówienie zakupu_.
1. Z listy sekwencji wybierz numer sekwencji 5 dla dyrektywy lokalizacji _51 Zamówienia bezpośrednie_.
1. Przenieś wybraną sekwencję w górę do numeru sekwencji 4.
1. Sprawdź, czy numer sekwencyji dyrektywy lokalizacji _QMS 51_ wynosi teraz co najmniej 5.

#### <a name="item-sampling"></a>Kontrola wyrywkowa pozycji

Funkcja _Zarządzania jakością dla procesów magazynowych_ dodaje nowe możliwości wyrywkowej kontroli towaru. Wartością **Zakres kontroli wyrywkowej** może być _Zamówienie_, _Wysyłka_ lub _Ładunek_, a wartość **Ilość kontroli wyrywkowej towarów** może być teraz _Pełny numer identyfikacyjny_.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Kontrola wyrywkowa towarów**.
1. Utwórz rekord kontroli wyrywkowej towaru i określ następujące wartości:

    - **Kontrola wyrywkowa pozycji** _Trzeci numer identyfikacyjny_
    - **Opis:** _Co trzeci numer identyfikacyjny_
    - **Zakres kontroli wyrywkowej:** _Zamówienie_

1. Na skróconej karcie **Ilość kontroli wyrywkowej towarów** ustaw pole **Specyfikacja ilości** na _Pełny numer identyfikacyjny_.
1. Na skróconej karcie **Proces** w polu **Na n-ty numer identyfikacyjny** należy określić wartość _3_.
1. W sekcji **Na wymiar magazynowania** włącz zarówno **Magazyn**, jak i **Stan zapasów**.

#### <a name="quality-associations"></a>Powiązania jakości

Utwórz skojarzenie jakości, które będzie korzystało z nowej wyrywkowej kontroli towarów.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Skojarzenia jakości**.
1. Utwórz rekord skojarzenia jakości i określ następujące wartości:

    - **Typ odwołania:** _Zakup_
    - **Kod pozycji:** _Tabela_
    - **Pozycja:** _M9201_
    - **Oddział:** _5_

1. Na skróconej karcie **Proces** w polu **Typ zdarzenia** należy określić wartość *Rejestracja*.
1. Na skróconej karcie **Warunki** ustaw pole **Odpowiedni typ magazynu** na *Tylko zarządzanie jakością dla procesów magazynowych*.
1. W skróconej karcie **Przetwarzanie zlecenia kontroli jakości** należy ustawić pole **Zasady przetwarzania jakości** na _Tworzenie zlecenia kontroli jakości_.
1. Na karcie skróconej **Specyfikacje** kliknij prawym przyciskiem myszy pole **Grupa testowa**, a następnie wybierz polecenie **Wyświetl szczegóły**, aby otworzyć stronę **Grupa testowa**.
1. Na stronie **Grupa testowa** na karcie **Przegląd** w górnej siatce utwórz grupę testową i określ następujące wartości:

    - **Grupa testowa:** _QMS_
    - **Opis:** _QMS test_
    - **Ilość akceptowalna:** _100_
    - **Kontrola wyrywkowa pozycji:** _Trzeci numer identyfikacyjny_ (Wybierz)

1. Na karcie **Przegląd** w dolnej siatce dodaj rekord dla jednego testu i określ następujące wartości:

    - **Sekwencja:** *1*
    - **Test:** *Mierzenie ogrodzenia*

1. Na karcie **Test** w dolnej siatce należy określić następujące wartości:

    - **Zmienne testowe:** *Sukces/Niepowodzenie*
    - **Wynik domyślny:** *Sukces*

1. Zapisz nową grupę testową i zamknij stronę **Grupy testowe**.
1. Wróć na stronie **Skojarzenia jakości**, w polu **Grupy testowe** wybierz opcję **QMS**.
1. Zapisz rekord.

#### <a name="mobile-device-menu-items-for-quality-in"></a>Elementy menu urządzeń mobilnych dla jakości wejściowej

Aby dokończyć konfigurowanie do przenoszenia towarów do lokalizacji kontroli jakości, należy ustawić, że dla elementu menu urządzenia przenośnego będzie dostępna wyrywkowa kontrola jakości towaru.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Wybierz element menu urządzenia przenośnego **Odłożenia zakupu**.
1. Na karcie skróconej **Klasy robocze** dodaj identyfikator klasy roboczej *QualityIn*.

#### <a name="summary-your-setup-to-move-goods-to-quality-control"></a>Podsumowanie: ustawienia dotyczące przenoszenia towarów do kontroli jakości

Zdefiniowane zostało teraz skojarzenie jakości, które używa funkcji *Zarządzania jakością dla procesów magazynowych*, aby wywołać tworzenie zlecenia kontroli jakości. Istnieje możliwość skonfigurowania pracy i danych lokalizacji dla magazynu 51 w celu zapewnienia, że podczas rejestracji zakupu dla pozycji M9201 są tworzone określone prace. Ta konfiguracja zapewnia, że każdy zarejestrowany trzeci numer identyfikacyjny zostanie przeniesiony do lokalizacji jakości (_QMS_), a zlecenie kontroli jakości zostanie utworzone dla ilości w numerze identyfikacyjnym. Pozostałe elementy zostaną przeniesione do odłożenia zamiast lokalizacji kontroli jakości.

### <a name="process-quality-management-work"></a>Praca przetwarzania zarządzania jakością

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Utwórz zamówienie zakupu i określ następujące wartości:

    - **Konto określonego dostawcy:** *104*
    - **Magazyn:** *51*

1. Dodaj wiersz zamówienia zakupu i określ następujące wartości:

    - **Pozycja:** *M9201*
    - **Ilość:** *20*
    - **JM:** *EA*
    - **Magazyn:** *51*

1. Zapisz numer zamówienia zakupu, tak aby można było go później wykorzystać.
1. Przejdź do urządzenia przenośnego lub emulatora, na którym uruchomiono aplikację Warehouse Management, i zaloguj się do magazynu 51, używając *51* jako identyfikatora użytkownika i *1* jako hasła.
1. Przejdź do **Przychodzące \>Przyjęcia zakupu** i wprowadź następujące wartości:

    - **PONum:** numer właśnie utworzonego zamówienia zakupu utworzonego
    - **Ilość:** *5*
    - **Jednostka:** *EA*

1. W dalszym ciągu pobieraj od wiersza *5 EA*, dopóki wiersz nie zostanie w pełni przyjęty. (Zostanie utworzone łącznie cztery numery identyfikacyjne.)
1. Wyloguj się z aplikacji mobilnej Warehouse Management.
1. Z powrotem w kliencie sieci Web wybierz kolejno **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Znajdź i otwórz zamówienie zakupu.
1. W sekcji **Wiersze zamówienia zakupu** wybierz wiersz dla kodu towaru *M9201*, a następnie wybierz **Wiersze zamówienia zakupu \> Szczegóły pracy**.
1. Należy zauważyć, że drugi i trzeci utworzony nagłówek pracy jest zwykłym działaniem odłożenia, podczas gdy pierwszy i czwarty nagłówek pracy jest pracą kontroli wyrywkowej jakości towaru. Wynik ten jest zgodny z konfiguracją kontroli wyrywkowej towarów, która jest konfigurowana do testowania każdego trzeciego numeru identyfikacyjnego.

#### <a name="move-to-the-quality-control-location"></a>Przejdź do lokalizacji kontroli jakości

Teraz zostaną przeniesione numery identyfikacyjne do ich wyznaczonych lokalizacji. Pierwsze i czwarte numery identyfikacyjne przejdą do lokalizacji kontroli jakości, natomiast drugi i trzeci numer identyfikacyjny pójdzie bezpośrednio do magazynu.

1. Przejdź do urządzenia przenośnego lub emulatora, na którym uruchomiono aplikację Warehouse Management, i zaloguj się do magazynu 51, używając *51* jako identyfikatora użytkownika i *1* jako hasła.
1. Przejdź do **Przychodzące \> Odłożenie zakupu** i odłóż każdy numer identyfikacyjnt z poprzedniej procedury aż do zamknięcia wszystkich prac.

#### <a name="summary-process-quality-management-work"></a>Podsumowanie: Praca przetwarzania zarządzania jakością

Teraz można uruchomić pracę wyrywkowej kontroli jakości towaru dla pierwszego i czwartego numeru identyfikacyjnego, przenosząc je do lokalizacji kontroli jakości. Również drugi i trzeci numer identyfikacyjny został odłożony. Następnym krokiem jest wykonanie testu zlecenia kontroli jakości i kontroli.

### <a name="quality-out-setup-move-from-the-quality-control-location-to-storage-or-return"></a>Konfiguracja jakości wychodzącej: przechodzenie z lokalizacji kontroli jakości do magazynu lub zwrotu

Podczas generowania wyników zlecenia kontroli jakości przez pracowników system automatycznie generuje pracę.

Teraz można kontynuować z użyciem wymaganej konfiguracji podstawowej klasy roboczej, szablonu pracy i dyrektywy lokalizacji, aby umożliwić zarządzanie jakością dla procesów magazynowych, tak aby można było utworzyć wymaganą pracę w celu przeniesienia ilości zlecenia kontroli jakości z lokalizacji kontroli jakości do wyznaczonej lokalizacji magazynowej.

#### <a name="work-class-for-quality-out"></a>Klasa robocza dla jakości wyjściowej

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Klasy robocze**.
1. Utwórz klasę roboczą i określ następujące wartości:

    - **Identyfikator klasy roboczej:** *QualityOut*
    - **Opis:** *Jakość wyjściowa*
    - **Typ zlecenia produkcyjnego:** *Zlecenie kontroli jakości*

#### <a name="work-templates"></a>Szablony pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. Zmień wartość **Typ zlecenia pracy** na *Zlecenie kontroli jakości*.
1. Utwórz szablon i określ następujące wartości:

    - **Szablon pracy:** *51 Jakość wyjściowa*
    - **Opis szablonu pracy:** *51 Jakość wyjściowa*

1. Dodaj wiersz i określ następujące wartości:

    - **Typ pracy:** *Pobranie*
    - **Identyfikator klasy roboczej:** **QualityOut**

1. Dodaj drugi wiersz i określ następujące wartości:

    - **Typ pracy:** *Odłożenie*
    - **Identyfikator klasy roboczej:** *QualityOut*

#### <a name="location-directives"></a>Dyrektywy lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. Zmień wartość **Typ zlecenia pracy** na *Zlecenie kontroli jakości*.
1. Utwórz dyrektywę lokalizacji i określ następujące wartości:

    - **Nazwa:** *51 Sukces*
    - **Typ pracy:** *Odłożenie*
    - **Oddział:** *5*
    - **Magazyn:** *51*

1. W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edycji kwerendy.
1. Na karcie **Zakres** ustaw następujące wartości:

    - **Tabela:** *Zlecenia kontroli jakości*
    - **Pole:** *Stan*
    - **Kryteria:** *Sukces*

1. Wybierz **OK**, zapisać kwerendę i zamknąć okno dialogowe.
1. Na skróconwej karcie **Wiersze** dodaj wiersz i określ następujące wartości:

    - **Od ilości:** *1*
    - **Do ilości:** *1000000*

1. Na skróconej karcie **Akcje dyrektywy lokalizacji** dodaj wiersz i określ następującą wartość:

    - **Nazwa:** *Sukces*

1. Na karcie skróconej **Akcje dyrektywy lokalizacji** kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edycji kwerendy.
1. Na karcie **Zakres** ustaw następujące wartości:

    - **Tabela:** *Lokalizacje*
    - **Pole:** *Identyfikator strefy*
    - **Kryteria:** *Zbiorcze*

1. Wybierz **OK**, zapisać kwerendę i zamknąć okno dialogowe.
1. W okienku akcji wybierz **Zapisz**, aby zapisać nową dyrektywę lokalizacji.
1. Utwórz drugą dyrektywę lokalizacji i określ następujące wartości:

    - **Nazwa:** *51 Niepowodzenie*
    - **Typ pracy:** *Odłożenie*
    - **Oddział:** *5*
    - **Magazyn:** *51*

1. W okienku akcji kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edycji kwerendy.
1. Na karcie **Zakres** ustaw następujące wartości:

    - **Tabela:** *Zlecenia kontroli jakości*
    - **Pole:** *Stan*
    - **Kryteria:** *Niepowodzenie*

1. Wybierz **OK**, zapisać kwerendę i zamknąć okno dialogowe.
1. Na skróconwej karcie **Wiersze** dodaj wiersz i określ następujące wartości:

    - **Od ilości:** *1*
    - **Do ilości:** *1000000*

1. Na skróconej karcie **Akcje dyrektywy lokalizacji** dodaj wiersz i określ następującą wartość:

    - **Nazwa:** *Niepowodzenie*

1. Na karcie skróconej **Akcje dyrektywy lokalizacji** kliknij opcję **Edytuj kwerendę**, aby otworzyć okno dialogowe edycji kwerendy.
1. Na karcie **Zakres** ustaw następujące wartości:

    - **Tabela:** *Lokalizacje*
    - **Pole:** *Identyfikator strefy*
    - **Kryteria:** *Zwrot*

1. Wybierz **OK**, zapisać kwerendę i zamknąć okno dialogowe.
1. W okienku akcji wybierz **Zapisz**, aby zapisać nową dyrektywę lokalizacji.

#### <a name="mobile-device-menu-items-for-quality-out"></a>Elementy menu urządzeń mobilnych dla jakości wyjściowej

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Wybierz element menu urządzenia przenośnego **QMS odłożenie**.
1. Na karcie skróconej **Klasy robocze** dodaj identyfikator klasy roboczej *QualityPut*.

Pracownicy magazynu będą teraz mogli pobierać pracę zlecenia kontroli jakości za pomocą elementu menu **QMS odłożenie**. Towary, które nie przeszły kontroli jakości, mogą zostać umieszczone w lokalizacji zwrotu, a przekazane towary można umieścić w lokalizacji masowe-001.

#### <a name="summary-your-setup-to-move-goods-from-quality-control"></a>Podsumowanie: ustawienia dotyczące przenoszenia towarów z kontroli jakości

Istnieje możliwość skonfigurowania pracy i danych lokalizacji dla magazynu 51 w celu zapewnienia automatycznego stworzenia pracy, gdy są zakończone zlecenia kontroli jakości. Ta konfiguracja zapewnia, że każdy numer identyfikacyjny kontrolowany przez jakość jest przenoszony do lokalizacji masowej lub lokalizacji zwrotu.

### <a name="process-quality-management-work"></a>Praca przetwarzania zarządzania jakością

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.
1. Umożliwia wybór pierwszego zlecenia kontroli jakości dla zarejestrowanych ilości.
1. Wybierz **Potwierdź**. Stan testu jest zaktualizowany do *Niepowodzenie*.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Cała praca**.
1. Otwórz właśnie utworzoną pracę i zwróć uwagę, że wartość **Typ zlecenia pracy** to *Zlecenie kontroli jakości*. Praca zawiera wiersz, w którym lokalizacja odłożenia to *Zwrot* i stan to *Niepowodzenie*. (Jeśli stan zlecenia kontroli jakości to *Sukces*, w zamian lokalizacja odłożenia wynosiłaby *Zbiorcze*.)
1. Wróć do **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.
1. Umożliwia wybór drugiego zlecenia kontroli jakości dla zarejestrowanych towarów.
1. Wybierz **Wyniki** powyżej dolnej siatki. Zaktualizuj wartość **Liczba wyników** na *5* i sprawdź, czy wartość **Wynik testu** ma znacznik wyboru.
1. Wybierz przycisk **Potwierdź** i zamknij stronę.
1. Wróć na stronie **Zlecenia kontroli jakości** wybierz pozycję **Potwierdź** i wykonaj weryfikację. Stan czeku jest zmieniany na *Sukces*.

    > [!NOTE]
    > Zdarzenie potwierdzania poprawności wyzwala utworzenie pracy zlecenia kontroli jakości w celu przeniesienia ilości z lokalizacji kontroli jakości do nowej lokalizacji.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Cała praca**.
1. Wybierz pracę, która została właśnie utworzona, i zwróć uwagę na to, że utworzono drugi nagłówek pracy zlecenia kontroli jakości, w którym znajduje się lokalizacja odłożenia *ZBIORCZE-001*.
1. Przejdź do urządzenia przenośnego lub emulatora, na którym uruchomiono aplikację Warehouse Management, i zaloguj się do magazynu 51, używając *51* jako identyfikatora użytkownika i *1* jako hasła.
1. Przejdź do **Jakość \> Odłóz z QMS** i przetwórz każdy z dwóch numerów identyfikacyjnych powiązanych z oboma częściami pracy, tak aby wszystkie prace zostały zamykane.

> [!NOTE]
> Rozważ dodanie wpisu jakości do elementu menu urządzenia przenośnego, w którym w kodzie działania jest *Wyświetl listę otwartych prac*. Na przykład zobacz pozycje menu urządzenia mobilnego o nazwie **Lista prac** w danych demonstracyjnych. Najpierw dodaj klasę roboczą *Zlecenie kontroli jakości* do elementu menu skierowanego do użytkownika, ponieważ ta klasa robocza jest wymagana do wyświetlenia pracy na liście prac. Następnie dodaj klasę roboczą *Zlecenie kontroli jakości* do elementu menu **Lista prac**. Użytkownicy, którzy mają dostęp do listy prac, będą mogli pobierać i przetwarzać pracę, która jest automatycznie generowana na podstawie weryfikacji zlecenia kontroli jakości.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie zarządzania kontrolą jakości i niezgodnością](quality-management-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]