---
title: Przewodnik po lokalizacji Dynamics 365 Commerce e-commerce
description: W tym artykule opisano, jak zlokalizować witrynę e-commerce Microsoft Dynamics 365 Commerce na dodatkowe języki i skonfigurować ją tak, aby obsługiwała wiele kanałów.
author: bicyclingfool
ms.date: 04/29/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 955a85340f6d35f1e203d74920d07b5dc6ff8654
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873391"
---
# <a name="dynamics-365-commerce-e-commerce-localization-guide"></a>Przewodnik po lokalizacji Dynamics 365 Commerce e-commerce

[!include [banner](includes/banner.md)]

Ten artykuł opisuje, jak zlokalizować witrynę e-commerce Microsoft Dynamics 365 Commerce na dodatkowe języki i skonfigurować ją do obsługi wielu kanałów, a także omawia pojęcia i terminologię związaną z tym procesem.

Możliwości e-commerce w Dynamics 365 Commerce zostały zaprojektowane tak, aby umożliwić doświadczenia online, które mogą być dostosowane do konkretnych krajów i języków, ale jednocześnie pozwalają na maksymalne ponowne wykorzystanie szablonów, stron, treści i mediów. Możesz też stworzyć podstawową witrynę, a następnie rozszerzać ją na nowe rynki, dodając z czasem obsługę kolejnych krajów i języków.

## <a name="definitions"></a>Definicje

**Lokalizacja, identyfikator lokalizacji**: Lokalizacja (inaczej identyfikator lokalizacji) określa język, który jest związany z danym krajem lub regionem. Na przykład identyfikator locale „fr-ca” jest związany z kanadyjskim językiem francuskim.

**Język podstawowy**: język, w którym tworzysz zawartość swojej strony przed jej wyeksportowaniem do lokalizacji.

**Kanał, sklep internetowy**: kanał (zwany też sklepem internetowym) definiuje metody płatności, grupy cenowe, hierarchie produktów, asortyment i produkty w internetowym sklepie e-commerce.

## <a name="concepts"></a>Koncepcje

### <a name="url-driven-experience"></a>Doświadczenie oparte na adresie URL

Serwisy e-commerce Dynamics 365 Commerce dostarczają klientom unikalnych doświadczeń rynkowych i lokalnych dzięki kanałom i identyfikatorom lokalizacji. Kanały określają unikalne dla danego rynku produkty, kategorie, waluty i metody płatności, a identyfikatory miejsc określają język treści, które widzą klienci. Witryna e-commerce używa adresów URL, by rozróżnić doświadczenia rynkowe i lokalne. Adresy URL witryny dla tych unikalnych kanałów i lokalizacji są definiowane dla witryny na stronie **Ustawienia witryny \> Kanały** w kreatorze witryn Dynamics 365 Commerce.

W kreatorze witryn adres URL jest kombinacją domeny i ścieżki, która definiuje punkt wejścia dla unikalnej kombinacji kanału i lokalizacji. W poniższym przykładzie fikcyjny sklep internetowy o nazwie Fabrikam Inc. definiuje cztery unikalne kombinacje kanału i lokalizacji, a następnie mapuje każdą z tych kombinacji na unikalny adres URL, który służy do serwowania treści klientom.

| Domena                     |  Ścieżka      | Kanał       |   Ustawienia regionalne     |
|------------------------|--------|--------------------------------|--------|
| `https://fabrikam.com` | /      | Fabrikam rozszerzył sklep internetowy | pl  |
| `https://fabrikam.com` | /es    | Fabrikam rozszerzył sklep internetowy | es     |
| `https://fabrikam.ca`  | /      | Sklep internetowy Contoso    | fr-ca  |
| `https://fabrikam.ca`  | /en-ca | Sklep internetowy Contoso    | en-ca  |

#### <a name="domain"></a>Domena

Domeny są tworzone podczas konfigurowania witryny e-commerce w Microsoft Dynamics Lifecycle Services (LCS). Po udostępnieniu środowiska e-commerce możesz dodać kolejne domeny, otwierając zgłoszenie serwisowe. Aby uzyskać więcej informacji o tym, jak skonfigurować domeny dla witryny e-commerce, zobacz [Domeny w Dynamics 365 Commerce](domains-commerce.md).

#### <a name="path"></a>Ścieżka

- Ścieżka to dowolny ciąg znaków, który w połączeniu z domeną jest mapowany na unikalną kombinację kanału i lokalizację. W poprzednim przykładzie łańcuch użyty jako ścieżka pasuje do identyfikatora lokalizacji, do którego ścieżka jest mapowana. Możesz jednak zastosować inne podejście.
- Kombinacja kanału i lokalizacji może być odwzorowana na domenę i pustą ścieżkę („/”). W poprzednim przykładzie klienci, którzy odwiedzą stronę `https://fabrikam.ca/`, otrzymają produkty i asortyment dla rynku kanadyjskiego w języku kanadyjskim francuskim.
- Kreator witryn Commerce uniemożliwia tworzenie duplikatów domeny i ścieżki. Możesz jednak mapować zduplikowane kombinacje kanału i locale na inną kombinację domeny i ścieżki.

#### <a name="channel"></a>Kanał

- Kanały (zwane też sklepami internetowymi) definiują metody płatności, grupy cenowe, hierarchie produktów, asortyment i produkty w internetowym sklepie e-commerce.
- Kanały są definiowane, konfigurowane i publikowane w centrali Dynamics 365 Commerce.
- Kreator witryn może wykryć sklepy internetowe, które zostały skonfigurowane w centrali Commerce i są dostępne do mapowania na witrynę.

Aby uzyskać więcej informacji na temat kanałów, zobacz [Przegląd kanałów](channels-overview.md). Aby uzyskać więcej informacji o tym, jak skonfigurować kanał online, zobacz [Konfigurowanie kanału online](channel-setup-online.md).

#### <a name="locale"></a>Ustawienia regionalne

- locale to rzeczywisty identyfikator używany podczas przekazywania plików XML Localization Interchange File Format (XLIFF) do lokalizacji. Języki lokalne są definiowane i publikowane dla każdego kanału w centrali Commerce. Informacje o tym, jak skonfigurować języki i kanały w programie budującym witrynę, znajdziesz w następnej sekcji.
- Ta sama lokalizacja może być przypisana do wielu kanałów. W ten sposób można zaoferować wspólny język na wielu rynkach.

## <a name="configure-languages-and-channels-for-your-e-commerce-site"></a>Skonfiguruj języki i kanały dla swojej witryny e-commerce

Po wyjęciu z pudełka wszystkie witryny e-commerce Dynamics 365 Commerce są skonfigurowane do korzystania z jednego kanału online i jednego języka, niezależnie od tego, czy zaczynasz od witryny demonstracyjnej Fabrikam, czy tworzysz nową witrynę od podstaw.

W takiej konfiguracji klienci i partnerzy zazwyczaj opracowują wszystkie zasoby, które będą używane w różnych krajach i językach. Aktywa te obejmują szablony, strony, fragmenty, treści i media. Cała zawartość witryny jest tworzona w pierwszym języku, który wybrałeś dla swojej witryny, lub jeśli korzystasz z witryny demonstracyjnej Fabrikam, zawartość witryny będzie tworzona w języku angielskim.

![Gotowa witryna e-commerce Dynamics 365 Commerce](media/loc-guide-1.png)

> [!NOTE]
> Możesz skonfigurować stronę demonstracyjną Fabrikam dla dodatkowego języka, tak aby tworzenie treści odbywało się w tym języku. Aby dowiedzieć się, jak dodać nowy język do witryny i kanału, zobacz sekcję [Konfiguracja dodatkowego języka dla witryny](#configure-an-additional-language-for-your-site) w dalszej części tego artykułu.

Jednak system zarządzania treścią (CMS) i model strony dla witryn e-commerce Dynamics 365 Commerce zostały zaprojektowane tak, aby umożliwić ekspansję na nowe rynki i lokalizacje. Dlatego za pośrednictwem jednej witryny e-commerce możesz zarządzać aktywami sklepu internetowego, który obejmuje wiele rynków i języków.

![Dynamics 365 Commerce – witryna e-commerce obejmująca wiele rynków i języków](media/loc-guide-2.png)

### <a name="configure-an-additional-language-for-your-site"></a>Skonfiguruj dodatkowy język dla swojej witryny

Proces konfigurowania nowego języka dla witryny e-commerce składa się z trzech kroków.

#### <a name="step-1-add-the-language-to-your-channel-online-store-in-commerce-headquarters"></a>Krok 1: Dodaj język do swojego kanału (sklepu internetowego) w centrali Commerce

1. W centrali Commerce przejdź do kanału, do którego chcesz dodać nowy język. Aby znaleźć listę kanałów, które skonfigurowałeś w centrali Commerce, przejdź do **Retail i Commerce \> Kanały \> Sklepy online**.
1. Otwórz sklep internetowy, który jest zmapowany do twojej strony, wybierając jego wartość **ID kanału Retail**. Możesz zweryfikować sklep internetowy, który jest zmapowany do twojej witryny, otwierając stronę ustawień witryny **Kanały** w kreatorze witryn Commerce i patrząc na nazwę sklepu internetowego w kolumnie **Kanały**. 
1. Na skróconej karcie **Języki** wybierz pozycję **Dodaj**. W polu **Język** wybierz kod locale dla nowego języka. Następnie kliknij przycisk **Zapisz**.
1. Przejdź do **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji** i uruchom zadanie **1070 Konfiguracja kanałów**. Kiedy zadanie zostanie wykonane, możesz przejść do kroku 2 i dodać język do kanału na swojej stronie w kreatorze stron.

![Języki skróconej karty sklepu internetowego w centrali Commerce](media/loc-guide-3.png)

#### <a name="step-2-add-the-language-to-a-channel-in-site-builder"></a>Krok 2: Dodaj język do kanału w kreatorze stron

Aby dodać język do kanału w narzędziu budowania witryny, wykonaj poniższe kroki.

1. W kreatorze witryn usługi Commerce otwórz witrynę, a następnie otwórz stronę **Kanały** w ustawieniach witryny.
1. Wybierz nazwę kanału, do którego chcesz dodać język.
1. W prawym okienku wybierz opcję **Dodaj lokalizację**.
1. W oknie dialogowym **Dodaj ustawienia**, w części **Dodaj ustawienia** wybierz ustawienia dla języka, który wcześniej dodałeś do kanału w centrali Commerce.
1. Wybierz domenę i ścieżkę, o którą będą prosić klienci, aby zobaczyć twoją stronę w tym kanale i języku.
1. Jeśli chcesz, aby ten język był domyślnym językiem przeglądania, tworzenia i aktualizowania stron i fragmentów kreatora witryn, zaznacz pole wyboru **Użyj jako domyślnego języka kanału autorskiego**. 
    > [!NOTE]
    > To ustawienie ma wpływ tylko na konstruktora witryny. Nie ma to wpływu na doświadczenia klientów związane z publikacją.
1. Kliknij przycisk **OK**.
1. Wybierz **Zapisz i opublikuj**.

#### <a name="step-3-localize-your-site-content"></a>Krok 3: Lokalizacja zawartości witryny

Kiedy wrócisz do widoku **Strony** w kreatorze witryn Commerce, nowy język będzie dostępny w oknie wyboru kanałów i lokalizacji w prawym górnym rogu. Możesz teraz tworzyć zlokalizowane wersje stron w swoim podstawowym języku.

Proces lokalizowania zawartości twoich stron i fragmentów jest opisany w sekcji [Lokalizacja zawartości witryny e-commerce](#localize-e-commerce-site-content) w dalszej części tego artykułu.

### <a name="configure-a-new-channel-for-your-site"></a>Skonfiguruj nowy kanał dla swojej witryny

Witryny e-commerce Dynamics 365 Commerce mogą obsługiwać doświadczenia zdefiniowane w wielu kanałach online, które są skonfigurowane w centrali Commerce. Strona wykorzystuje wiele kanałów, by pokazać klientom unikalną konfigurację metod płatności, grup cenowych, hierarchii produktów, asortymentu i zestawu produktów. Kanał jest zwykle wykorzystywany do konfigurowania tych wymiarów, aby dopasować je do wymagań i preferencji dotyczących doświadczeń związanych z poszczególnymi krajami. Takie podejście jest jednak decyzją biznesową, którą podejmuje klient. To nie jest wymóg.

Warunki wstępne i zadania związane z tworzeniem kanału (sklepu internetowego) wykraczają poza zakres tego dokumentu. Aby uzyskać więcej informacji o tym, jak skonfigurować kanał online w centrali Commerce, zobacz [Podstawy konfiguracji kanałów](channels-overview.md#channel-setup-basics). Aby uzyskać informacje o krokach i wymaganiach specyficznych dla kanałów online, zobacz [Konfigurowanie kanału online](channel-setup-online.md).

Aby dodać kanał do swojej witryny w programie budującym witrynę, wykonaj poniższe kroki.

1. W kreatorze witryn Commerce przejdź do **Ustawień witryny \> Kanały**. 
1. Wybierz **Dodaj kanał**.
1. W oknie dialogowym **Dodaj kanał**, w części **Kanał** wybierz kanał, który chcesz dodać. 
    > [!NOTE]
    > Możesz dodać tylko te kanały, które nie zostały jeszcze dodane na twojej stronie.
1. Wybierz domyślne ustawienia lokalne dla kanału. Jeśli dodasz do kanału nowe języki, możesz zmienić język domyślny na jeden z nich.
1. Określ domenę i ścieżkę, które będą stanowiły adres URL służący do serwowania treści i doświadczeń dla tej kombinacji kanału i języka.
1. Kliknij przycisk **OK**.
1. Wybierz **Zapisz i opublikuj**.

## <a name="localize-e-commerce-site-content"></a>Zlokalizuj zawartość strony e-commerce

### <a name="xliff-basics"></a>Podstawy XLIFF

XLIFF jest standardowym formatem plików służącym do przekazywania zlokalizowanej zawartości pomiędzy narzędziami do zarządzania treścią. Kreator witryn Commerce używa formatu XLIFF do eksportowania zawartości metadanych stron, fragmentów i obrazków, aby można je było zlokalizować i ponownie zaimportować.

Klienci Microsoft Dynamics zazwyczaj współpracują z zewnętrznymi dostawcami usług lokalizacyjnych, takimi jak [Translated.com](https://translated.com/welcome), aby przetłumaczyć pliki XLIFF na wymagane języki.

### <a name="localize-assets-in-site-builder"></a>Zlokalizuj zasoby w kreatorze witryn

Następujące elementy witryny e-commerce mogą zostać zlokalizowane w programie do budowania witryn:

- Strony
- Fragmenty
- Zasoby medialne
- Moduły

Wszystkie nowe strony, fragmenty i zasoby medialne są tworzone w kontekście kanału i języka, które są aktualnie wybrane w selektorze kanałów i lokalizacji. Ten język jest zwykle twoim językiem podstawowym, pod warunkiem, że nie skonfigurowałeś dodatkowych języków lub kanałów. Na stronach, na których skonfigurowano wiele kanałów i języków, język bazowy jest określany przez kanał i locale, które ustawiłeś jako domyślne na stronie **Kanały** w ustawieniach strony.

Kroki związane z lokalizowaniem zawartości stron, fragmentów i zasobów medialnych są podobne. Wyjątki i różnice zostaną wskazane w kolejnych rozdziałach. Jednak kroki podejmowane w celu zlokalizowania zawartości modułu różnią się. Aby uzyskać więcej informacji, zobacz sekcję [Lokalizowanie modułów](#localize-modules) w dalszej części tego artykułu.

#### <a name="step-1-export-an-xliff-file"></a>Krok 1: Eksportowanie pliku XLIFF

Aby wyeksportować plik XLIFF dla strony, fragmentu lub obrazu w narzędziu budowania witryny, wykonaj poniższe kroki.

1. Otwórz zasób, dla którego chcesz wyeksportować zawartość w języku podstawowym, aby można ją było zlokalizować.
1. Na pasku poleceń wybierz **Lokalizacja \> Eksport XLIFF**.
    > [!NOTE]
    > Opcja **Lokalizacja** jest widoczna tylko wtedy, gdy zasób jest w stanie **Edytuj**.

Do folderu pobierania w przeglądarce zostanie pobrany plik XLIFF o nazwie **\<assetname\>.xlf**. Ten plik XLIFF jest specyficzny dla zasobów, które lokalizujesz. Wyeksportujesz plik XLIFF dla każdego zasobu, który chcesz zlokalizować.

#### <a name="step-2-localize-the-xliff-file"></a>Krok 2: Lokalizacja pliku XLIFF

W większości przypadków będziesz współpracował z dostawcą usług lokalizacyjnych, który przetłumaczy twoje pliki XLIFF. Jeśli jednak lokalizujesz zasoby wewnętrznie lub chcesz po prostu przetestować proces lokalizacji, musisz dokonać następujących zmian w pliku XLIFF:

- Dodaj atrybut target language do elementu /xliff/file i ustaw jego wartość na identyfikator lokalizacji języka, na który dokonujesz lokalizacji. 
    > [!NOTE]
    > Ten identyfikator locale musi odpowiadać identyfikatorowi locale ze strony **Kanały** w ustawieniach witryny.
- Dla każdego elementu //source dodaj element docelowy (target element sibling), w którym wartość tekstowa jest zlokalizowaną wersją zawartości tego elementu źródłowego.

Informacje o schemacie rządzącym plikami XLIFF można znaleźć w dokumencie [Specyfikacja XLIFF 1.2](http://docs.oasis-open.org/xliff/xliff-core/xliff-core.html).

> [!NOTE]
> Aby zlokalizować zasób na wiele języków, musisz utworzyć zlokalizowany plik XLIFF dla każdego z tych języków.

#### <a name="step-3-import-the-localized-xliff-file"></a>Krok 3: Importowanie zlokalizowanego pliku XLIFF

Aby zaimportować plik XLIFF dla danego zasobu, wykonaj poniższe kroki.

1. W kreatorze witryn Commerce otwórz zasób, dla którego chcesz zaimportować plik XLIFF.
1. W oknie wyboru kanałów i wersji językowych w prawym górnym rogu wybierz kanał i język, dla którego importujesz zlokalizowane treści.
1. Na pasku poleceń wybierz **Lokalizacja \> Import XLIFF**. Następnie przejrzyj i wybierz zlokalizowany plik XLIFF dla wybranego zasobu i języka.

Po pomyślnym zaimportowaniu pliku XLIFF tworzony jest wariant strony, fragmentu lub zasobu. Od tego momentu wszystkie zmiany dokonywane w wariancie zlokalizowanym będą dotyczyły tylko tego wariantu. Nie będą one miały wpływu na zasób podstawowy, z którego powstał wariant. Podobnie zmiany w podstawowym zasobie nie będą miały wpływu na wariant tego zasobu. 

Jednak w przypadku stron możesz wprowadzać zmiany w różnych wariantach, modyfikując szablon lub układ, do którego strony są przypisane. Podobnie zmiany we fragmencie będą miały wpływ na wszystkie strony, które przyjmują zależność od tego wariantu.

### <a name="images"></a>Obrazy

Obrazy mogą być renderowane w wariancie strony lub modułu tylko wtedy, gdy metadane treści związane z tymi obrazami są zlokalizowane. Obecnie można zlokalizować następujące metadane w aktywach medialnych:

- Tekst alternatywny
- Opis
- Tytuł

Obecnie nie można zlokalizować binarnego zasobu cyfrowego, takiego jak obraz czy film. Zespół produktu Dynamics 365 Commerce pracuje obecnie nad tą możliwością.

### <a name="localize-modules"></a>Zlokalizuj moduły

Ciągi, które są renderowane jako część samego modułu (na przykład „Poprzedni” i „Następny” w module karuzeli), są lokalizowane oddzielnie od zawartości modułu. Aby uzyskać instrukcje, zobacz [Zlokalizuj moduł](e-commerce-extensibility/localize-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Słownik terminów dotyczących modelu strony](page-elements-overview.md)

[Współdzielenie kanałów](cross-channel-sharing.md)

[Lokalizacja modułu](e-commerce-extensibility/localize-module.md)

[Plik definicji modułu](e-commerce-extensibility/module-definition-file.md)

[Lokalizowanie zasobów rozszerzeń rozwiązania Commerce i plików etykiet](dev-itpro/extension-resource-localization.md)

[Globalizacja modułów za pomocą klasy CultureInfoFormatter](e-commerce-extensibility/globalize-modules.md)

[Ustawienia aplikacji: Motywy](e-commerce-extensibility/app-settings.md#themes-section)
