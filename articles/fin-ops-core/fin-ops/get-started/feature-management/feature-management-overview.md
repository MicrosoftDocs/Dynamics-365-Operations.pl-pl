---
title: Zarządzanie funkcjami — omówienie
description: W tym temacie opisano funkcję zarządzania funkcjami i sposób jego używania.
author: ChrisGarty
manager: AnnBe
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: a0f7391273e2374bdd136c5db47bcb65487e2a9c
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798360"
---
# <a name="feature-management-overview"></a>Zarządzanie funkcjami — omówienie

[!include [banner](../../includes/banner.md)]

Funkcje są dodawane i aktualizowane w każdym wydaniu. Środowisko zarządzania funkcjami udostępnia obszar roboczy, w którym można wyświetlić listę funkcji, które zostały dostarczone w każdej wersji. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich.

## <a name="the-feature-management-workspace"></a>Obszar roboczy Zarządzanie funkcjami

Obszar roboczy **zarządzanie funkcjami** można otworzyć, wybierając odpowiedni kafelek na pulpicie nawigacyjnym. Zobaczysz stronę, która zawiera listę funkcji dla wszystkich wersji, które są obsługiwane przez funkcję zarządzania funkcjami. Z biegiem czasu firma Microsoft zwiększy funkcjonalność zarządzania funkcjami, tak aby były dostępne kolejne funkcje do łatwiejszego zarządzania funkcjami.

Lista funkcji zawiera następujące informacje:

- **Nazwa funkcji** — opis dodanej funkcji.
- **Stan włączony** — symbol wskazuje, czy funkcja została włączona (znacznik wyboru), nie została włączona (pusta), została zaplanowana do włączenia (zegar) lub jest obowiązkowo włączona (blokada), wymaga uwagi przed włączeniem (ostrzeżenie) lub nie może zostać włączony (X). Pokazane ustawienie jest używane dla wszystkich firm. Należy pamiętać, że nawet wtedy, gdy funkcja została włączona, jest nadal kontrolowana przez zabezpieczenia. W związku z tym funkcja będzie dostępna tylko dla użytkowników, którzy mają do niej dostęp, na podstawie ich roli zabezpieczeń. Będzie ona również dostępna tylko w firmach, do których użytkownik ma dostęp.
- **Data włączenia** — data, kiedy funkcja została włączona lub jest zaplanowana do włączenia.
- **Dodano funkcję** – data, kiedy funkcja została dodana do danego środowiska. Ta data jest automatycznie wprowadzana podczas aktualizowania środowiska podczas comiesięcznych wydań.
- **Moduł** — moduł, którego dotyczy nowa funkcja.

Po wybraniu funkcji w okienku szczegółów po prawej stronie listy funkcji pojawią się dodatkowe informacje. W górnej części okienka zobaczysz nazwę funkcji, datę dodania funkcji, moduł, którego dotyczy ta funkcja, oraz łacze **Dowiedz się więcej**. Wybierz to łącze, aby wyświetlić dokumentację dla tej funkcji. Jeśli dokumentacja nie jest dostępna, nastąpi przekierowanie do strony tymczasowej. Okienko szczegółów zawiera również pole **komentarzy**, w którym można dodawać własne komentarze dotyczące tej funkcji.

Obszar roboczy **Zarządzanie funkcjami** zawiera również kilka kart i na każdej z nich jest wyświetlona lista funkcji.

- **Nowe** — na tej karcie są pokazane wszystkie funkcje, które zostały dodane od czasu ostatniej aktualizacji miesięcznej. Jeśli użytkownik pominął comiesięczne aktualizacje, na karcie są pokazane wszystkie nowe funkcje, które zostały dodane od czasu ostatniej aktualizacji. Najnowsze funkcje są wyświetlane na górze listy. Całkowita liczba nowych funkcji jest również wyświetlana na kafelku u góry strony.
- **Nie włączono** — na tej karcie są pokazane wszystkie funkcje, które nie zostały włączone. Najnowsze funkcje są wyświetlane na górze listy. Całkowita liczba nowych funkcji, które nie zostały włączone, jest również podana na kafelku u góry strony.
- **Zaplanowane** — na tej karcie są pokazane wszystkie funkcje, które zostały zaplanowane do włączenia w przyszłości. Funkcje, które mają najwcześniejszą zaplanowaną datę znajdują się u góry listy. Całkowita liczba nowych zaplanowanych funkcji jest również wyświetlana na kafelku u góry strony.
- **Wszystkie** — na tej karcie są pokazane wszystkie funkcje. Najnowsze funkcje są wyświetlane na górze listy.

## <a name="turn-on-a-feature"></a>Włączanie funkcji

Jeśli funkcja nie została włączona, w okienku szczegółów zostanie wyświetlony przycisk **Włącz teraz**. Za pomocą tego przycisku można włączyć funkcję.

- Wybierz funkcję, którą chcesz włączyć, a następnie w okienku szczegółów naciśnij przycisk **Włącz teraz**. Funkcja jest włączona.

Niektóre funkcje nie mogą zostać wyłączone po ich włączeniu. Jeśli funkcja, którą próbujesz włączyć, nie może zostać wyłączona, zostanie wyświetlone ostrzeżenie. W tym momencie możesz nacisnąć przycisk **Anuluj**, aby anulować operację i pozostawić funkcję wyłączoną. Jeśli jednak wybierzesz opcję **Włącz**, aby włączyć funkcję, nie będzie można jej później wyłączyć.

Niektóre funkcje będą wyświetlały komunikat, który zawiera dodatkowe informacje, zanim je włączysz. Funkcje te są oznaczone żółtym symbolem ostrzegawczym. Należy uważnie przeczytać dodatkowe informacje, aby lepiej zrozumieć, co się stanie, gdy funkcja jest włączona. Jednak nadal można wybrać **Włącz**, aby włączyć funkcję.

Niektóre funkcje będą wyświetlał komunikat, że funkcja nie może być włączona, dopóki nie zostanie podjęta akcja. Funkcje te są oznaczone czerwonym symbolem X. Przed uaktywnieniem tej funkcji należy wykonać czynności opisane w opisie. Na przykład jeśli nie można użyć funkcji do momentu wyłączenia klucza konfiguracji, należy najpierw wyłączyć klucz konfiguracji, a następnie powrócić do funkcji Zarządzanie funkcją, aby włączyć tę funkcję.

Po włączeniu tej funkcji w okienku szczegółów zostanie wyświetlony komunikat poniżej łącza **Dowiedz się więcej**. Ten komunikat informuje, że funkcja została włączona lub wskazuje przyszłą datę, na kiedy jest zaplanowane włączenie funkcji. Ta wiadomość pojawia się za każdym razem, gdy wybierzesz funkcję na liście funkcji.

Funkcje zaplanowane do włączenia w przyszłości pojawią się na karcie **Zaplanowane**. Proces wsadowy będzie je włączać o północy danego dnia na podstawie strefy czasowej reprezentowanej przez datę systemową.

## <a name="reschedule-a-feature"></a>Zmiana harmonogramu funkcji

Jeśli zaplanowano włączenie funkcji w przyszłości, w okienku szczegółów jest wyświetlany przycisk **Zaplanuj**. Można użyć tego przycisku, aby zmienić wartość **Data włączenia**.

1. Wybierz zaplanowaną funkcję, której plan chcesz zmienić, a następnie w okienku szczegółów naciśnij przycisk **Planuj.**
2. W wyświetlonym oknie dialogowym, w polu **Data włączenia** określ nową datę włączenia funkcji.
3. Wybierz opcję **Włącz**, aby ponownie zaplanować operację lub **wyłącz**, aby anulować harmonogram.

## <a name="turn-off-a-feature"></a>Wyłączanie funkcji

Jeśli funkcja została już włączona, w okienku szczegółów jest wyświetlany przycisk **Wyłącz**. Za pomocą tego przycisku można wyłączyć funkcję. Przycisk **Wyłącz** jest niedostępny, jeśli po włączeniu funkcji nie można jej wyłączyć.

- Wybierz funkcję, którą chcesz wyłączyć, a następnie w okienku szczegółów naciśnij przycisk **Wyłącz.** Funkcja zostanie wyłączona, a pole **Data włączenia** zostanie opróżnione.

Po wyłączeniu tej funkcji w okienku szczegółów zostanie wyświetlony komunikat poniżej łącza **Dowiedz się więcej**. Ten komunikat stwierdza, że funkcja nie została jeszcze włączona. Ta wiadomość pojawia się za każdym razem, gdy wybierzesz funkcję na liście funkcji. Funkcje, które nie są włączone, są wyświetlane na karcie **Nie włączono**.

## <a name="features-that-must-be-turned-on"></a>Funkcje, które muszą być włączone

Czasami jest dostarczana krytyczna funkcja, która musi zostać włączona automatycznie po wykonaniu aktualizacji. Te funkcje będą włączane automatycznie w dniu określonym w polu **Data włączenia**. W przypadku tych funkcji w okienku szczegółów zostanie wyświetlony komunikat poniżej łącza **Dowiedz się więcej**. Ten komunikat informuje, że funkcja została włączona lub wskazuje przyszłą datę, kiedy zostanie ona włączona. Ta wiadomość pojawia się za każdym razem, gdy wybierzesz funkcję na liście funkcji.

## <a name="enable-all-features"></a>Włącz wszystkie funkcje

Domyślnie wszystkie funkcje dodawane do środowiska są wyłączone. Wszystkie funkcje można włączyć, zaznaczając przycisk **Włącz wszystkie**. 

Po wybraniu **Włącz wszystkie**, opcja pojawi się tam, gdzie potrzebujesz podać następujące informacje:
- Lista wszystkich funkcji, które wymagają potwierdzenia, zanim będą mogły być włączone. Jeśli chcesz włączyć funkcje z list, wybierz **Tak** dla przycisku **Włącz funkcje wymagające potwierdzenia**.
- Zostanie wyświetlona lista wszystkich funkcji, które nie mogą być włączone. Te funkcje nie zostaną włączone.

Wszystkie funkcje, które mogą być włączone, zostaną włączone. Jeśli funkcja została już zaplanowana do włączenia w przyszłości, harmonogram nie zmieni się. 

## <a name="turn-on-all-features-automatically"></a>Automatyczne włączanie wszystkich funkcji

Domyślnie wszystkie funkcje dodawane do środowiska są wyłączone, o ile nie są obowiązkowe. Jeśli jednak chcesz, aby wszystkie nowe funkcje były automatycznie włączane, możesz użyć listy rozwijanej pod tytułem obszaru roboczego, aby zmienić to, co dzieje się przy dodawaniu nowych funkcji.

- Wybierz opcję `Enable new features automatically`, aby wszystkie nowe funkcje były automatycznie włączane po dodaniu ich do Twojego środowiska.
- Wybierz opcję `Do not enable new features automatically`, aby domyślnie wszystkie nowe funkcje były automatycznie wyłączane po dodaniu ich do Twojego środowiska.


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

## <a name="new-features-are-optional-for-12-months"></a>Nowe funkcje są opcjonalne przez 12 miesięcy

Jeśli zainstalowana zostanie nowa funkcja niekrytyczna, korzystanie z niej jest opcjonalne przez okres 12 miesięcy. Dzięki temu użytkownik i jego organizacja mają czas na zaplanowanie wdrożenia funkcji i przetestowania jej w ramach codziennych operacji. Aby uzyskać więcej informacji, zobacz [Aktualizacje do jednej wersji usługi – często zadawane pytania](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/one-version#what-about-new-features).

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Korzystanie z funkcji Zarządzanie funkcjami w celu włączania funkcji ISV lub funkcji niestandardowych

Zarządzanie funkcjami nie jest obecnie dostępne dla funkcji pochodzących od niezależnych dostawców oprogramowania (ISV) i funkcji niestandardowych. Jednak firma Microsoft rozszerza możliwości Zarządzania funkcjami. Po zakończeniu tych ulepszeń firma Microsoft będzie udostępniać Zarządzanie funkcjami dla wszystkich funkcje i przekaże instrukcje aktualizowania posiadanych funkcji, aby były obsługiwane przez Zarządzanie funkcjami.

## <a name="frequently-asked-questions-faq"></a>Często zadawane pytania (FAQ)

### <a name="when-are-features-added-removed-or-changed"></a>Kiedy są dodawane, usuwane lub zmieniane są funkcje? 
Funkcje są dodawane, usuwane i zmieniane za pomocą zmian kodu. Aby te zmiany zostały wprowadzone, należy zaktualizować środowiska.

### <a name="does-a-feature-become-mandatory-automatically"></a>Czy funkcja staje się obowiązkowa automatycznie? 
Nie, zamiana funkcji w obowiązkową nie jest akcją automatyczną. Zespoły produktów muszą dokonać zmiany kodu.

### <a name="when-do-features-become-mandatory"></a>Kiedy funkcje stają się obowiązkowe? 
Zasada polega na tym, że wszystkie nowe funkcje będą obowiązywać przez okres 12 miesięcy i nie będzie konieczne zarządzanie zmianami, dopóki ta funkcja nie zostanie włączona. Zespoły produktów mogą określić, czy funkcja ma być obowiązkowa po zakończeniu tego okresu. 

### <a name="why-isnt-there-a-specific-mandatory-enabled-date"></a>Dlaczego nie istnieje określona „obowiązkowa data włączenia"? 
Czas wydania aktualizacji jest zmienny, czas aktualizacji środowiska jest zmienny, a klienci mogą zdecydować się na pominięcie niektórych aktualizacji. W wyniku tego trudno jest ustalić konkretne daty. 

### <a name="wheres-the-documentation-for-features-that-are-being-made-mandatory"></a>Gdzie jest dokumentacja funkcji, które są wprowadzane jako obowiązkowe? 
Dokumentacja pochodzi od zespołów aplikacji. Często są one wymienione w [usuniętych lub przestarzałych funkcjach](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features). 

### <a name="is-there-an-in-product-notification-or-signal-that-a-feature-is-going-to-be-mandatory-enabled"></a>Czy istnieje powiadomienie dotyczące produktu lub sygnał, że funkcja jest wymagana do włączenia? 
Mechanizm powiadamiania związany z wprowadzaniem wymaganej funkcji nie istnieje dzisiaj.

### <a name="do-features-ever-get-enabled-without-the-customer-knowing-about-it"></a>Czy funkcje zostały kiedykolwiek włączone bez wiedzy klienta? 
Tak, jeśli funkcje nie mają wpływu funkcjonalnego, mogą być wyłączone domyślnie.

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