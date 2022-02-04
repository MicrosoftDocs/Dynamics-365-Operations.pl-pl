---
# required metadata
title: Zarządzanie funkcjami — omówienie
description: W tym temacie opisano funkcję zarządzania funkcjami i sposób jego używania.
author: Peakerbl
ms.date: 01/10/2022
ms.topic: overview
ms.prod: null
ms.technology: null
ms.search.form: FeatureManagementWorkspace
audience: 'IT Pro, Application user'
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom:
  - month/year of release that feature was introduced in
  - in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
---

# <a name="feature-management-overview"></a>Zarządzanie funkcjami — omówienie

[!include [banner](../../includes/banner.md)]

Funkcje są dodawane i aktualizowane w każdym wydaniu. Środowisko zarządzania funkcjami udostępnia obszar roboczy, w którym można wyświetlić listę funkcji, które zostały dostarczone w każdej wersji. Następnie można użyć obszaru roboczego do wyświetlania dokumentacji funkcji oraz włączania lub wyłączania funkcji.

## <a name="the-feature-management-workspace"></a>Obszar roboczy Zarządzanie funkcjami

Obszar roboczy **zarządzanie funkcjami** można otworzyć, wybierając odpowiedni kafelek na pulpicie nawigacyjnym. Zobaczysz stronę, która zawiera listę funkcji dla wszystkich wersji, które są obsługiwane przez funkcję zarządzania funkcjami. 

Lista funkcji zawiera następujące informacje:

- **Nazwa funkcji** — opis dodanej funkcji.
- **Stan** — symbol wskazuje, czy funkcja została włączona (znacznik wyboru), została włączona (pusta), została zaplanowana do włączenia (zegar) lub jest obowiązkowo włączona (kłódka), wymaga uwagi przed włączeniem (ostrzeżenie) lub nie może zostać włączona (X). Pokazane ustawienie jest używane dla wszystkich firm. Należy pamiętać, że nawet wtedy, gdy funkcja została włączona, jest nadal kontrolowana przez zabezpieczenia. W związku z tym funkcja będzie dostępna tylko dla użytkowników, którzy mają do niej dostęp, na podstawie ich roli zabezpieczeń. Będzie ona również dostępna tylko w firmach, do których użytkownik ma dostęp.
- **Data włączenia** — data, kiedy funkcja została włączona lub jest zaplanowana do włączenia.
- **Dodano funkcję** – data, kiedy funkcja została dodana do danego środowiska. Ta data jest automatycznie wprowadzana podczas aktualizowania środowiska podczas comiesięcznych wydań.
- **Stan funkcji** — bieżący stan cyklu życia funkcji: **Podgląd**, **Wydana** (pokazane jako puste), **Domyślnie włączona** i **Obowiązkowa**. Stany są omówione bardziej szczegółowo w dalszej części tego tematu. 
- **Moduł** — moduł, którego dotyczy nowa funkcja.

> [!NOTE]
> Kolumna **Stan funkcji** jest dostępna od wersji 10.0.21.

Po wybraniu funkcji w okienku szczegółów po prawej stronie listy funkcji pojawią się dodatkowe informacje. W górnej części okienka zobaczysz nazwę funkcji, datę dodania funkcji, moduł, którego dotyczy ta funkcja, oraz łacze **Dowiedz się więcej**. Wybierz to łącze, aby wyświetlić dokumentację dla tej funkcji. Jeśli dokumentacja nie jest dostępna, nastąpi przekierowanie do strony tymczasowej. Okienko szczegółów zawiera również pole **komentarzy**, w którym można dodawać własne komentarze dotyczące tej funkcji.

Obszar roboczy **Zarządzanie funkcjami** zawiera również kilka kart i na każdej z nich jest wyświetlona lista funkcji.

- **Nowe** — na tej karcie są pokazane wszystkie funkcje, które zostały dodane od czasu ostatniej aktualizacji miesięcznej. Jeśli użytkownik pominął comiesięczne aktualizacje, na karcie są pokazane wszystkie nowe funkcje, które zostały dodane od czasu ostatniej aktualizacji. Najnowsze funkcje są wyświetlane na górze listy. Całkowita liczba nowych funkcji jest również wyświetlana na kafelku u góry strony.
- **Nie włączono** — na tej karcie są pokazane wszystkie funkcje, które nie zostały włączone. Najnowsze funkcje są wyświetlane na górze listy. Ponadto kafelek w górnej części strony pokazuje całkowitą liczbę nowych funkcji, które są obecnie wyłączone.
- **Zaplanowane** — na tej karcie są pokazane wszystkie funkcje, które zostały zaplanowane do włączenia w przyszłości. Funkcje, które mają najwcześniejszą zaplanowaną datę znajdują się u góry listy. Co więcej, całkowita liczba nowych zaplanowanych funkcji jest również wyświetlana na kafelku u góry strony.
- **Wszystkie** — na tej karcie są pokazane wszystkie funkcje. Najnowsze funkcje są wyświetlane na górze listy.

## <a name="feature-states"></a>Stany elementów
Funkcje mogą przechodzić pomiędzy kilkoma stanami, od wprowadzenia w zarządzaniu cechami, aż do stania się obowiązkowymi w produkcie. W tej sekcji opisano prawidłowe stany funkcji.

### <a name="preview-features-optional"></a>Funkcje w wersji zapoznawczej (opcjonalnie)

Zespoły produktów mogą zdecydować się na uruchomienie nowej funkcji jako funkcji w wersji zapoznawczej. Funkcje podglądu nie są domyślnie włączone i są opcjonalne. Zespół produktu, który jest właścicielem, zaktualizuje funkcje do wydania po pomyślnym okresie wersji zapoznawczej.

> [!NOTE]
> Funkcje w wersji zapoznawczej podlegają określonym [warunkom wersji zapoznawczej](https://go.microsoft.com/fwlink/?linkid=2105274). 

### <a name="released-features-optional"></a>Wydane funkcje (opcjonalnie)

Kolumna **Stan funkcji** dla tych funkcji jest pusta. Funkcje, które są początkowo dodawane jako wydane, nie są domyślnie włączone, a ich włączenie jest opcjonalne. Funkcje, które są aktualizowane z wersji zapoznawczej zachowają stan włączenia.

### <a name="on-by-default-features-optional"></a>Funkcje domyślnie włączone (opcjonalnie)

Funkcje, które są **domyślnie włączone**, są domyślnie włączone, ale można je wyłączyć. Po tym jak funkcje, które mogą być wyłączone, będą w stanie **Wydane** przez co najmniej sześć miesięcy, oczekuje się, że przejdą do tego stanu w następnym dużym wydaniu. Funkcje, które przechodzą do **Domyślnie włączone** powinny być opisane w sekcji [Co nowego](../whats-new-changed.md) dla danej wersji. Aktualizacja jest inicjowana przez zespół będący właścicielem produktu.

> [!NOTE]
> Ponieważ funkcje te zostaną włączone automatycznie, ważne jest, abyś określił, czy Twoja organizacja jest gotowa na ich wykorzystanie, czy też potrzeba na to więcej czasu. Jeśli potrzeba więcej czasu, może być konieczne tymczasowe wyłączenie tych funkcji. Należy zauważyć, że przejście funkcji do **Domyślnie włączona** odbywa się w głównej wersji, zanim funkcja ma stać się **obowiązkowa**. W tym momencie nie będzie można wyłączyć tej funkcji. 

### <a name="mandatory"></a>Wymagana

**Wymagana** jest oczekiwanym stanem końcowym funkcji. Informuje on, że funkcje są włączone i nie można ich wyłączyć bez kontaktu z firmą Microsoft. Opcjonalne funkcje mają stać się obowiązkowe po dwóch głównych wersjach. Funkcje krytyczne mogą, w drodze wyjątku, zostać wprowadzone jako obowiązkowe.

## <a name="example-of-expected-feature-lifecycles"></a>Przykład oczekiwanych cykli życia operacji

Funkcje, które można wyłączyć i które zostały dodane jako wydane i opcjonalne przed lub w ramach wydania kwietniowego, powinny domyślnie przejść na **Włączone domyślnie** w następnej wersji październikowej. Oczekuje się, że staną się one **Obowiązkowe** w kwietniu następnego roku.

Funkcje, których nie można wyłączyć i które zostały dodane jako wydane i opcjonalne przed lub w ramach wydania kwietniowego, powinny domyślnie przejść na **Obowiązkowe** w następnej wersji kwietniowej.

## <a name="enable-a-feature"></a>Włączanie funkcji

Jeśli funkcja nie została włączona, w okienku szczegółów zostanie wyświetlony przycisk **Włącz teraz**. Za pomocą tego przycisku można włączyć tę funkcję.

Niektóre funkcje nie mogą być wyłączone po ich włączeniu. Jeśli funkcja, którą próbujesz włączyć, nie może zostać wyłączona, zostanie wyświetlone ostrzeżenie. W tym momencie możesz wybrać **Anuluj**, aby anulować operację i pozostawić tę funkcję wyłączoną. Jeśli jednak wybierzesz opcję **Włącz** i włączysz tę funkcję, nie będzie można jej później wyłączyć.

Niektóre funkcje będą wyświetlały komunikat, który zawiera dodatkowe informacje, zanim je włączysz. Funkcje te są oznaczone żółtym symbolem ostrzegawczym. Należy uważnie przeczytać dodatkowe informacje, aby lepiej zrozumieć, co się stanie, gdy funkcja jest włączona. Jednak nadal można wybrać **Włącz**, aby włączyć funkcję.

Niektóre funkcje będą wyświetlał komunikat, że funkcja nie może być włączona, dopóki nie zostanie podjęta akcja. Funkcje te są oznaczone czerwonym symbolem X. Przed uaktywnieniem tej funkcji należy wykonać czynności opisane w opisie. Na przykład jeśli nie można użyć funkcji do momentu wyłączenia klucza konfiguracji, należy najpierw wyłączyć klucz konfiguracji, a następnie powrócić do funkcji Zarządzanie funkcją, aby włączyć tę funkcję.

Po włączeniu tej funkcji w okienku szczegółów zostanie wyświetlony komunikat poniżej łącza **Dowiedz się więcej**. Ten komunikat informuje, że funkcja została włączona lub wskazuje przyszłą datę, na kiedy jest zaplanowane włączenie funkcji. Ta wiadomość pojawia się za każdym razem, gdy wybierzesz funkcję na liście funkcji.

Funkcje zaplanowane do włączenia w przyszłości pojawią się na karcie **Zaplanowane**. Proces wsadowy będzie je włączać o północy danego dnia na podstawie strefy czasowej reprezentowanej przez datę systemową.

## <a name="reschedule-a-feature"></a>Zmiana harmonogramu funkcji

Jeśli zaplanowano włączenie funkcji w przyszłości, w okienku szczegółów jest wyświetlany przycisk **Zaplanuj**. Można użyć tego przycisku, aby zmienić wartość **Data włączenia**.

1. Wybierz zaplanowaną funkcję, której plan chcesz zmienić, a następnie w okienku szczegółów naciśnij przycisk **Planuj.**
2. W wyświetlonym oknie dialogowym, w polu **Data włączenia** określ nową datę włączenia funkcji.
3. Wybierz opcję **Włącz**, aby ponownie zaplanować operację lub **wyłącz**, aby anulować harmonogram.

## <a name="disable-a-feature"></a>Wyłączanie funkcji

Jeśli funkcja została już włączona, w okienku szczegółów zostanie wyświetlony przycisk **Wyłącz**. Za pomocą tego przycisku można wyłączyć tę funkcję. Przycisk **Wyłącz** jest niedostępny, jeśli po włączeniu tej funkcji nie można jej wyłączyć. 

Po włączeniu tej funkcji w okienku szczegółów zostanie wyświetlony komunikat poniżej łącza **Dowiedz się więcej**. Ten komunikat stwierdza, że funkcja nie została jeszcze włączona. Ta wiadomość pojawia się za każdym razem, gdy wybierzesz funkcję na liście funkcji. Funkcje, które nie są włączone, są wyświetlane na karcie **Nie włączono**.

## <a name="features-that-must-be-enabled"></a>Funkcje, które muszą być włączone

Czasami jest dostarczana krytyczna funkcja, która musi zostać włączona automatycznie po wykonaniu aktualizacji. Te funkcje będą włączane automatycznie w dniu określonym w polu **Data włączenia**. W przypadku tych funkcji w okienku szczegółów zostanie wyświetlony komunikat poniżej łącza **Dowiedz się więcej**. Ten komunikat informuje, że funkcja została włączona lub wskazuje, kiedy funkcja zostanie włączona w przyszłości. Ta wiadomość pojawia się za każdym razem, gdy wybierzesz funkcję na liście funkcji.

## <a name="enable-all-features"></a>Włącz wszystkie funkcje

Wszystkie funkcje można włączyć, zaznaczając przycisk **Włącz wszystkie**. 

Po wybraniu **Włącz wszystkie**, opcja pojawi się tam, gdzie potrzebujesz podać następujące informacje:

- Lista wszystkich funkcji, które wymagają potwierdzenia, zanim będą mogły być włączone. Jeśli chcesz włączyć funkcje z list, wybierz **Tak** dla przycisku **Włącz funkcje wymagające potwierdzenia**.
- Zostanie wyświetlona lista wszystkich funkcji, które nie mogą być włączone. Te funkcje nie zostaną włączone.

Wszystkie funkcje, które mogą być włączone, zostaną włączone. Jeśli funkcja została już zaplanowana do włączenia w przyszłości, harmonogram nie zmieni się. 

## <a name="enable-all-features-automatically"></a>Automatyczne włączanie wszystkich funkcji

Jeśli jednak chcesz, aby wszystkie nowe funkcje były automatycznie włączane, możesz użyć listy rozwijanej pod tytułem obszaru roboczego, aby zmienić to, co dzieje się przy dodawaniu nowych funkcji.

- Wybierz opcję **Wszystkie nowe funkcje będą domyślnie włączone**, jeśli chcesz aby wszystkie nowe funkcje były automatycznie włączane po dodaniu ich do Twojego środowiska.
- Wybierz opcję **Wszystkie nowe funkcje będą domyślnie wyłączone**, jeśli chcesz aby wszystkie nowe funkcje były automatycznie wyłączane po dodaniu ich do Twojego środowiska.

Jeśli włączysz wszystkich funkcji automatycznie, spowoduje to włączenie wszystkich funkcji, które byłyby włączone, po kliknięciu przycisku **Włącz wszystkie**. Nie zostaną włączone funkcje wymagające potwierdzenia lub funkcje, które nie mogą być włączone, dopóki nie zostanie podjęta akcja.

## <a name="check-for-updates"></a>Sprawdź, czy są aktualizacje

Funkcje są dodawane do środowiska po każdej aktualizacji. Można jednak ręcznie sprawdzić dostępność aktualizacji, klikając przycisk **Sprawdź aktualizacje.** Każda funkcja dodana do systemu po aktualizacji zostanie dodana do listy funkcji. Na przykład w przypadku włączenia funkcji testowej po jej wydaniu, można sprawdzić, czy są dostępne aktualizacje i funkcja zostanie dodana do Twojej listy.

## <a name="assigning-roles"></a>Przypisywanie ról

Obszar roboczy **Zarządzanie funkcjami** mogą otwierać administratorzy systemu i użytkownicy przypisani do roli Menedżer funkcji lub roli Podgląd funkcji. Te dwie role zostały utworzone w celu obsługi zarządzania funkcjami. Użytkownicy w roli Menedżera funkcji mogą włączać i wyłączać dowolne funkcje. Mogą również aktualizować pole **Komentarze** funkcji. Użytkownicy w roli podglądu funkcji mogą wyświetlać tylko obszar roboczy **zarządzanie funkcją**. Nie mogą włączać ani wyłączać funkcji.

Rola Menedżera funkcji i roli podglądu funkcji nie zastępują istniejących zabezpieczeń przypisanych do użytkownika. Kontrolują one tylko, czy użytkownik może włączać i wyłączać funkcje. Nie zapewniają dostępu do samych funkcji.

## <a name="features-that-use-configuration-keys"></a>Funkcje korzystające z kluczy konfiguracji

Jeśli funkcja korzysta z klucza konfiguracji, ale klucz konfiguracji nie jest włączony, obszar roboczy **Zarządzanie funkcjami** nie pokazuje tej funkcji na liście dostępnych funkcji. Po włączeniu klucza konfiguracji należy zaktualizować listę funkcji przy użyciu opcji menu **Wyszukaj aktualizacje**. Wtedy funkcja zostanie wyświetlona na liście funkcji.

Po wyłączeniu klucza konfiguracji funkcja nie zostanie usunięta z listy funkcji.

## <a name="data-entities"></a>Jednostki danych

Jednostka danych o nazwie **Zarządzanie funkcjami** umożliwia eksportowanie ustawień zarządzania funkcją z jednego środowiska, a następnie importowanie ich do innego środowiska. Ta jednostka aktualizuje tylko istniejące funkcje. Logika biznesowa w jednostce pomaga również zagwarantować, że po zakończeniu importu zostaną zastosowane te same reguły, które są używane w obszarze roboczym **Zarządzanie funkcjami**. Na przykład nie można zastąpić obowiązkowych ustawień funkcji, usuwając datę podczas importowania.

Poniższe przykłady opisują, co się dzieje w przypadku importowania danych przy użyciu jednostki **Zarządzanie funkcjami**.

- Zmiana wartości pola **Włączone** na **Tak** powoduje włączenie funkcji oraz wstawienie bieżącej daty w polu **Data włączenia**.
- Zmiana wartości pola **Włączone** na **Nie** lub pozostawienie pola **Data włączenia** pustego powoduje wyłączenie funkcji oraz opróżnienie pola **Data włączenia**. Nie można wyłączyć obowiązkowej funkcji lub funkcji, która nie może zostać wyłączona po jej włączeniu.
- Zmana wartości pola **Data włączenia** na datę przyszłą powoduje zaplanowanie funkcji na tę datę.
- Zmiana wartości pola **Włączone** na **Tak** i zmiana wartości pola **Data włączenia** na datę przyszłą powoduje zaplanowanie funkcji na tę datę. 
- Zmiana wartości pola **Włączone** na **Nie** równocześnie ze zmianą wartości pola **Data włączenia** na datę przyszłą powoduje zaplanowanie funkcji na tę datę.
- Jeśli funkcja jest włączona i zostanie dodane pole **Data włączenia** z datą przyszłą, funkcja pozostanie włączona. Aby zmienić zaplanowaną datę funkcji, należy zmienić wartość w polu **Włączone** na **Nie**.

## <a name="feature-management-and-flighting"></a>Zarządzanie funkcją i dystrybucja testowa

Zarządzanie funkcjami umożliwia kontrolowanie funkcji, które są dostarczane w poszczególnych wersjach. Dystrybucja testowa umożliwia Microsoft Teams udostępnianie funkcji ograniczonej liczbie klientów, dzięki czemu funkcje mogą być testowane i weryfikowane bez wpływu na wszystkich klientów. Zarządzanie funkcjami nie kontroluje dystrybucji testowej żadnych funkcji.

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Korzystanie z funkcji Zarządzanie funkcjami w celu włączania funkcji ISV lub funkcji niestandardowych

Zarządzanie funkcjami nie jest obecnie dostępne dla funkcji pochodzących od niezależnych dostawców oprogramowania (ISV) i funkcji niestandardowych. Jednak firma Microsoft rozszerza możliwości Zarządzania funkcjami. Po zakończeniu tych ulepszeń firma Microsoft będzie udostępniać Zarządzanie funkcjami dla wszystkich funkcje i przekaże instrukcje aktualizowania posiadanych funkcji, aby były obsługiwane przez Zarządzanie funkcjami.

## <a name="frequently-asked-questions-faq"></a>Często zadawane pytania (FAQ)

### <a name="when-are-features-added-removed-or-changed"></a>Kiedy są dodawane, usuwane lub zmieniane są funkcje? 
Funkcje są dodawane, usuwane i zmieniane za pomocą zmian kodu przez zespoły będące właścicielem produktu. Aby te zmiany zostały wprowadzone, należy zaktualizować środowiska.

### <a name="does-a-feature-become-mandatory-automatically"></a>Czy funkcja staje się obowiązkowa automatycznie? 
Nie, ta funkcja nie staje się obowiązkowa automatycznie. Zespół odpowiedzialny za produkt musi dokonać zmiany kodu.

### <a name="why-isnt-there-a-specific-mandatory-enabled-date"></a>Dlaczego nie istnieje określona „obowiązkowa data włączenia"? 
Czas wydania aktualizacji jest zmienny, czas aktualizacji środowiska jest zmienny, a klienci mogą zdecydować się na pominięcie niektórych aktualizacji. W wyniku tego trudno jest ustalić konkretne daty. 

### <a name="wheres-the-documentation-for-features-that-are-mandatory"></a>Gdzie jest dokumentacja funkcji, które są obowiązkowe? 
Dokumentacja ta pochodzi od każdego zespołu ds. aplikacji Dynamics 365. Często te funkcje będą wymienione w [aktualizacjach do stanów funkcji klienta](/dynamics365-release-plan/2021wave1/finance-operations/finance-operations-crossapp-capabilities/updates-client-feature-states) albo [usuniętych lub przestarzałych funkcjach](../../../dev-itpro/migration-upgrade/deprecated-features.md). 

### <a name="is-there-an-in-product-notification-or-signal-that-a-feature-is-going-to-be-mandatory-enabled"></a>Czy istnieje powiadomienie dotyczące produktu lub sygnał, że funkcja jest wymagana do włączenia? 
Mechanizm powiadamiania związany z wprowadzaniem wymaganej funkcji nie istnieje dzisiaj.

### <a name="do-features-ever-get-enabled-without-the-customer-knowing-about-it"></a>Czy funkcje zostały kiedykolwiek włączone bez wiedzy klienta? 
Tak, funkcje mogą zostać włączone bez wiedzy klienta w następujących sytuacjach:
- Funkcja jest przenoszona do **Domyślnie włączona**. W tym stanie funkcję nadal można wyłączyć. 
- Funkcja jest aktualizowana do **Obowiązkowa**. Ta zmiana nastąpi tylko w połączeniu z wydaniem głównym. Funkcje krytyczne mogą, w drodze wyjątku, zostać przeniesione do stanu **Obowiązkowa** w każdej aktualizacji.

### <a name="what-is-feature-flighting-and-how-does-it-relate-to-feature-management"></a>Co to jest funkcja wylotu i w jaki sposób wiąże się ona z zarządzaniem funkcjami? 
Usuwanie funkcji to przełączniki w czasie rzeczywistym włączone/wyłączone kontrolki Microsoft. Są one niezależne od kontrolki odbiorcy udostępnianej przez Zarządzanie funkcjami. 
- Funkcje prywatnej wersji zapoznawczej nie będą wymieniane w Zarządzaniu funkcjami, dopóki nie zostaną włączone. W procesie produkcji odbiorca musi wyrazić zgodę na część specjalnego programu, który ma zostać wyprowadzony.
- Funkcje publicznej wersji zapoznawczej i wydanej (ogólnie dostępne) będą wyświetlane na liście Zarządzanie funkcjami, chyba że zostaną usunięte. Opuszczenie funkcji jest uważane za ostateczność dla zespołów produktowych, jeśli zostanie wykryty krytyczny problem i zwykle będzie to operacja wykonywana przez jednego klienta.

### <a name="do-features-ever-get-flighted-off-without-the-customer-knowing-about-it"></a>Czy funkcje zostały kiedykolwiek opuszczone bez wiedzy klienta? 
Tak, jeśli funkcja wpływa na funkcjonowanie środowiska, które nie ma wpływu funkcjonalnego, może być domyślnie włączona.

### <a name="how-can-feature-enablement-be-checked-in-code"></a>Jak sprawdzić włączenie funkcji w kodzie?
Należy zastosować metodę **isFeatureEnabled** w klasie **FeatureStateProvider**, przekazując do niej instancję klasy funkcji. Przykład: 

```xpp
if (FeatureStateProvider::isFeatureEnabled(BatchContentionPreventionFeature::instance()))
```

### <a name="how-can-feature-enablement-be-checked-in-metadata"></a>Jak sprawdzić włączenie funkcji w metadanych?
Właściwość **FeatureClass** może służyć do wskazania, że niektóre metadane są skojarzone z funkcją. Należy użyć nazwy klasy używanej dla funkcji, np **BatchContentionPreventionFeature**. Metadane są widoczne tylko w tej funkcji. Właściwość **FeatureClass** jest dostępna w menu, elementach menu, wartościach tekstu stałego oraz polach tabel/widoków.

### <a name="what-is-a-feature-class"></a>Co to jest klasa funkcji?
Funkcje w Zarządzaniu funkcjami są zdefiniowane jako *klasy funkcji*. Klasa funkcji **implementuje IFeatureMetadata** i używa atrybutu klasy funkcji w celu identyfikacji się w obszarze roboczym Zarządzanie funkcjami. Istnieje wiele przykładów dostępnych klas funkcji, które można sprawdzać pod kątem włączenia w kodzie za pomocą interfejsu API **FeatureStateProvider** i metadanych, używając właściwości **FeatureClass**. Przykład: 

```xpp
[ExportAttribute(identifierStr(Microsoft.Dynamics.ApplicationPlatform.FeatureExposure.IFeatureMetadata))]
internal final class BankCurrencyRevalGlobalEnableFeature implements IFeatureMetadata
```

### <a name="what-is-the-ifeaturelifecycle-implemented-by-some-feature-classes"></a>Co to jest implementacja IFeatureLifecycle przez niektóre klasy funkcji?
IFeatureLifecycle jest wewnętrznym mechanizmem Microsoft określającym etap cyklu funkcji. Funkcje mogą być następujące:
- `PrivatePreview` — wymaga, aby pakiet testowy był widoczny.
- `PublicPreview` — wyświetlana domyślnie, ale z ostrzeżeniem, że funkcja jest w wersji zapoznawczej.
- `Released`— całkowicie wydane.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
