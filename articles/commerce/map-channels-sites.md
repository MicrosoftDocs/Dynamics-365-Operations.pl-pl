---
title: Mapowanie kanałów na witryny handlu elektronicznego
description: W tym temacie opisano niektóre bardziej typowe scenariusze mapowania kanału w Microsoft Dynamics 365 Commerce, które można ekstrapolowane w przypadku większości innych wymagań biznesowych.
author: samjarawan
ms.date: 05/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8ce272d63b4a37f99661333a02434708205ea19a
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743583"
---
# <a name="map-channels-to-e-commerce-sites"></a>Mapowanie kanałów na witryny handlu elektronicznego

W tym temacie opisano niektóre bardziej typowe scenariusze mapowania kanału w Microsoft Dynamics 365 Commerce, które można ekstrapolowane w przypadku większości innych wymagań biznesowych.

Dynamics 365 Commerce obsługuje wiele scenariuszy biznesowych do mapowania [kanałów online](#channels) ze skonfigurowanym zestawem produktów, [cen i rabatów na doświadczenia w witrynach e-commerce](#e-commerce-sites) dla odbiorców.

W tym temacie omówiono następujące scenariusze:

- **Kanał w jednym języku z jedną witryną w portalu e-commerce.** Na przykład ten scenariusz może dotyczyć jednej witryny marki, która jest skonfigurowana dla rynku amerykańskiego w Języku angielskim.
- **Kanał wielojęzyczny z jedną zlokalizowaną witryną.** Na przykład ten scenariusz może obejmować witrynę jednej marki skonfigurowaną dla Kanady z obsługą języka francuskiego i angielskiego. W tym scenariuszu użytkownicy, którzy wybierają różne języki, mają takie samo środowisko witryny, ale są zlokalizowane w wybranym języku każdego użytkownika.
- **Kanał wielojęzyczny, w którym witryna różni się w zależności od języka.** Na przykład ten scenariusz może obejmować witrynę jednej marki skonfigurowaną dla Kanady z obsługą języka francuskiego i angielskiego. W tym scenariuszu występują unikatowe doświadczenia w lokacji dla każdego języka.
- **Wiele kanałów (jednojęzycznych i/lub wielojęzycznych) z jedną lokalizacjią witryny.** Na przykład ten scenariusz może obejmować witrynę jednej marki skonfigurowaną dla Australii i Nowej Zelandii. W tym scenariuszu oba kraje mają takie same doświadczenie w lokacji w języku angielskim, ale każdy kraj jest skonfigurowany z innymi produktami, walutą, cenami, rabatami i trybami wysyłki.
- **Wiele kanałów (jednojęzycznych i/lub wielojęzycznych), które różnią się wyglądem strony na kanał.** Na przykład ten scenariusz może obejmować witrynę jednej marki, która jest skonfigurowana dla Australii, Kanady i Niemiec w wielu językach. W tym scenariuszu każdy kraj ma unikalne środowisko witryny, które jest skonfigurowane z różnymi produktami, walutą, cenami, rabatami i trybami wysyłki.

## <a name="channels"></a>Kanały

Kanał (znany także jako sklep internetowy lub kanał online) reprezentuje sklep internetowy e-commerce, który jest używany do mapowania produktów, cen, rabatów, języków, metod płatności, metod dostawy, centrów realizacji i innych aspektów doświadczenia w trybie online, które będą dostępne dla odbiorców w handlu elektronicznym. Kanały są tworzone i zarządzane w programie Commerce Headquarters i mapowane na pojedynczą [firmę](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json#legal-entities). Firma zazwyczaj ma siedzibę w jednym kraju, który wymaga raportowania podatku dla kanału i może być skonfigurowana tylko w jednej walucie.

Aby uzyskać więcej informacji na temat kanałów, zobacz [Przegląd kanału](channels-overview.md). Aby uzyskać więcej informacji o tym, jak skonfigurować kanał online, zobacz [Konfigurowanie kanału online](channel-setup-online.md).

Poniższa przykładowa ilustracja z centrali Commerce przedstawia domyślne kanały online, które są wdrażane z Dynamics 365 Commerce, jeśli wybrano opcję danych demonstracyjnych.

![Domyślne demonstracyjne kanały danych w Commerce headquarters.](media/channel-mapping-1.png)

## <a name="e-commerce-sites"></a>Witryny handlu elektronicznego

Witryna e-commerce zawiera zestaw stron witryny, których klienci używają do przeglądania i zakupów. Witryny w portalu E-commerce są zarządzane w Konstruktorze witryn portalu Commerce.

Aby uzyskać więcej informacji na temat tworzenia witryn i zarządzania nimi w narzędziu do tworzenia witryn, zobacz [Omówienie witryn handlu elektronicznego](online-store-overview.md).

## <a name="common-channel-mapping-scenarios"></a>Typowe scenariusze mapowania kanału

Dynamics 365 Commerce oferuje wiele scenariuszy mapowania kanałów. Scenariusze mapowania kanału, które nas śledzą, są tylko podzestawem wszystkich możliwych scenariuszy mapowania kanału. Te scenariusze pomagają w planowaniu dowolnych unikatowych scenariuszy biznesowych. Fikcyjny sklep sportowy Adventure Works, który jest dołączony do danych demonstracyjnych Dynamics 365 Commerce, jest używany jako przykład dla każdego scenariusza.

### <a name="single-language-channel-that-has-a-single-e-commerce-site-experience"></a>Kanał w jednym języku z jedną witryną w portalu e-commerce

W najbardziej podstawowym scenariuszu jeden kanał ma jeden język do sprzedaży na jednym rynku. Przykładem takiego scenariusza jest sklep internetowy Adventure Works, który jest przeznaczony wyłącznie na rynek amerykański.

Poniższy przykład ilustruje konfigurację kanałów w centrali Commerce headquarters. W tej konfiguracji kanał internetowy obsługuje tylko jeden język (**en-us**), jedną walutę (**USD**) i jeden podmiot gospodarczy (**usrt**), który jest używany do celów sprawozdawczości podatkowej.

![Wartości firmy, waluty i języka sklepu internetowego Adventure Works są wyróżnione w programie Commerce Headquarters.](media/channel-mapping-3.png)

Pojedynczy kanał online może być mapowany na pojedynczą witrynę e-commerce w Konstruktorze witryn. Aby uzyskać informacje dotyczące sposobu tworzenia nowej witryny i mapowania jej na kanał, zobacz temat [Mapowanie kanału na witrynę w sekcji Konstruktora witryn tego tematu](#map-a-channel-to-a-site-in-site-builder).

### <a name="multi-language-channel-that-has-a-single-localized-site-experience"></a>Kanał wielojęzyczny z jedną zlokalizowaną witryną

W tym scenariuszu jeden kanał obsługuje więcej niż jeden język. Dzięki temu nazwy, opisy i atrybuty produktów mogą być zlokalizowane w programie Commerce Headquarters. Aby zapewnić pełną lokalizacji witryny, zawartość marketingową w tej witrynie można także zlokalizowanych w Konstruktorze witryn portalu Commerce.

Ograniczeniem tego scenariusza jest to, że jeden kanał można skonfigurować tylko przy użyciu jednej waluty, jednej firmy i jednego zestawu produktów i cen. Ta konfiguracja działa najlepiej w przypadku krajów, w których jest jedna waluta i wiele języków (na przykład Kanada, w której dostępne są języki angielski i francuski), jedna firma oraz jeden zestaw produktów i cen.

Każdy język w kanale można skonfigurować przy użyciu własnej nazwy domeny. Na przykład, domena `www.adventure-works.ca` może być skonfigurowana dla kanadyjskiej wersji angielskiej, a domena `www.adventure-works-fr.ca` może być skonfigurowana dla kanadyjskiej wersji francuskiej. Można również skonfigurować różne języki w kanale w jednej domenie, a następnie używać innej ścieżki dla każdego języka. Na przykład, domena `www.adventure-works.ca` może być skonfigurowana dla kanadyjskiej wersji angielskiej, a następnie ścieżka `www.adventure-works.ca/fr` może być użyta dla kanadyjskiej wersji francuskiej. [Wykrywanie geograficznej](geo-detection-redirection.md) można również włączyć, aby automatycznie przekierowyywać użytkownika do właściwej witryny, zgodnie z jego lokalizacją.

Aby uzyskać informacje dotyczące sposobu włączania ręcznego przełączania odbiorców między językami, zobacz [sekcję Dodawanie i konfigurowanie modułu skonsutora](#add-and-configure-the-site-picker-module) witryny w tym temacie. Aby uzyskać informacje dotyczące dostosowywania zlokalizowanych stron i fragmentów, [zobacz temat Zarządzanie zawartością witryny, która ma wiele kanałów i sekcji języków](#manage-site-content-that-has-multiple-channels-and-languages).

### <a name="multi-language-channel-that-has-a-different-site-experience-per-language"></a>Kanał wielojęzyczny, w którym witryna różni się w zależności od języka

Może być preferowany scenariusz, w którym jeden kanał obsługuje więcej niż jeden język, ale dla każdego języka jest renderowane całkowicie inne doświadczenie w lokacji. Zalecaną metodą implementacji tego scenariusza jest użycie wariantów [strony](#implement-page-variants-for-each-language) w jednym witrynie.

Inną metodą jest utworzenie nowej witryny w portalu e-commerce dla każdego języka w Konstruktorze witryn, a następnie zamapowanie każdej witryny na jeden kanał i język online. W wyniku tego zostanie pojedynczy kanał online mapowany na wiele witryn e-commerce, po jednym dla każdego języka. Ta metoda wieloodpowiedzialności wymaga dodatkowych zasobów zarządzania, ponieważ w Konstruktorze witryn będzie można zarządzać więcej niż jedną witryną.

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-single-localized-site-experience"></a>Wiele kanałów (jednojęzycznych i/lub wielojęzycznych) z jedną lokalizacjią witryny

Witryna pod marką może wymagać obsługi wielu kanałów online w poszczególnych regionach, aby obsługiwać inną walutę, zestaw produktów oraz zestaw cen dla każdego kanału w jednej witrynie. Na przykład witryna adventure Works może mieć kanał online dla rynku kanadyjskiego, który ma wiele języków, kanał dla rynku amerykańskiego, który ma jeden język, oraz kanał dla rynku niemieckiego, który ma jeden język. W tym scenariuszu każdy kanał online zostanie skonfigurowany dla firmy specyficznej dla regionu i może mieć ten sam zestaw produktów, który mają inne kanały, podzestaw tych produktów lub inny zestaw produktów. Dla każdego kanału są również dostępne ceny w walucie lokalnej, podatkach, rabatach i trybach wysyłki.

W tym scenariuszu każdy rynek może być skonfigurowany z własnymi nazwami domen. Na przykład domena `www.adventure-works.com` może być skonfigurowana na rynek amerykański, a domena `www.adventure-works.de` może być skonfigurowana na rynek niemiecki. Każdy rynek można również skonfigurować tak, aby wykorzystywał inną ścieżkę. Na przykład domena `www.adventure-works.com` może być skonfigurowana na rynek amerykański, a następnie ścieżkę `www.adventure-works.com/de` można użyć dla rynku niemieckiego. [Wykrywanie geograficznej](geo-detection-redirection.md) można również włączyć, aby automatycznie przekierowywać użytkowników do właściwej witryny w zależności od regionu.

Witryna może również zawierać listę rozwijaną, która umożliwia użytkownikom ręczne przełączanie na określony rynek. Aby uzyskać więcej informacji, zobacz sekcję [Dodaj i skonfiguruj moduł selektora witryn](#add-and-configure-the-site-picker-module) w następnej części tego tematu.

Aby uzyskać informacje dotyczące konfigurowania wielu kanałów w jednej witrynie, zobacz sekcję [Konfigurowanie wielu kanałów w sekcji witryny handlu elektronicznego](#configure-multiple-channels-on-an-e-commerce-site).

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-different-site-experience-per-channel"></a>Wiele kanałów (jednojęzycznych i/lub wielojęzycznych), które różnią się wyglądem strony na kanał

W różnych regionach może być chcieć mieć wiele kanałów dla jednej marki, a w każdym regionie mieć inne doświadczenie w lokacji. Istnieją dwie metody implementowania tego scenariusza:

- Użyj [wariantów strony](#implement-page-variants-for-each-language).
- Skonfiguruj inną witrynę dla każdego kanału online w Konstruktorze witryn, a następnie zamapuj każdą witrynę na inny kanał i język online. Ta metoda wymaga dodatkowych zasobów zarządzania, ponieważ w Konstruktorze witryn będzie można zarządzać więcej niż jedną witryną.

## <a name="cross-channel-sharing"></a>Współdzielenie kanałów

Udostępnianie między kanałami jest przydatne, gdy wiele kanałów w jednym oddziale może udostępniać zawartość. Na przykład sprzedawca, który ma wiele marek i sklepów zgrupowanych w jednym oddziale, może udostępniać część zawartości niektórych lub wszystkich sklepów. Ta udostępniona zawartość może zawierać strony dotyczące warunków i postanowień, warunków płatności, metod wysyłki i często zadawanych pytań (FAQ). Aby uzyskać więcej informacji, zobacz Temat [Włączania i używania udostępniania między kanałami](cross-channel-sharing.md).

## <a name="map-a-channel-to-a-site-in-site-builder"></a>Mapowanie kanału na witrynę w Konstruktorze witryn

Istnieje wiele metod tworzenia i konfigurowania witryn, aby używać różnych kanałów w trybie online.

### <a name="create-a-new-site"></a>Stworzyć nową witrynę

Nową witrynę w Konstruktorze witryn można utworzyć, przechodząc na stronę **listy Witryny** i wybierając pozycję **Nowa witryna**. Następnie w wyświetlonym oknie dialogowym **Nowa witryna** można wybrać domyślny kanał i język witryny, tak jak pokazano na poniższej przykładowej ilustracji.

![Tworzenie nowego kanału w Konstruktorze witryn.](media/channel-mapping-4.png)

Witryna tworzyć w ten sposób będzie pusta i nie będzie zawierać żadnych stron witryny (na przykład strony głównej, stron kategorii i stron produktów).

Aby uzyskać więcej informacji, przejrzyj temat [Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md).

### <a name="create-a-new-site-by-using-the-site-copy-operation"></a>Utwórz nowy witrynę za pomocą operacji kopiowania witryny

Zamiast tworzyć nową, pustą witrynę, jak opisano w poprzedniej sekcji, lepiej jest rozpocząć od kopii jednego z początkowych witryn przedstawionych w bibliotece modułów Commerce, takiego jak Fabrikam czy Adventure Works.

Aby skopiować istniejącą witrynę, przejdź **do strony listy Witryny** w Konstruktorze witryn i wybierz pozycję **Kopiuj witrynę**. Następnie w wyświetlonym oknie dialogowym **Kopiuj witrynę** można wybrać witrynę źródłową i określić nazwę witryny docelowej.

Na tym etapie nie można wybrać domyślnego kanału i języka online dla witryny. Można je jednak skonfigurować po zakończeniu operacji kopiowania w witrynie. Po pierwszym wybraniu witryny na stronie listy **Witryny** w **Konstruktorze witryn** zostanie wyświetlone okno dialogowe Konfiguracja witryny, w którym możesz wybrać domyślny kanał i język.

Aby uzyskać więcej informacji na temat operacji kopiowania witryny, zobacz [Kopiowanie witryny handlu elektronicznego](copy-ecommerce-site.md).

### <a name="manage-an-existing-site-channel"></a>Zarządzanie istniejącym kanałem witryny

Po skonfigurowaniu kanału w witrynie można nim zarządzać i aktualizować go z poziomu wybranej witryny w programie budującym witrynę pod adresem **Ustawienia witryny \> Kanały**, jak pokazano na poniższej ilustracji.

![Zarządzanie mapowaniem kanałów w Konstruktorze witryn.](media/channel-mapping-7.png)

## <a name="support-multiple-sites-in-a-single-tenant"></a>Obsługa wielu witryn w jednym dzierżawie

Wiele markowanych witryn może współistnieć w jednym dzierżawie. Na poniższej ilustracji przedstawiono trzy różne witryny o różnych markach (Adventure Works, Adventure Works Business i Fabrikam), z których każdy jest mapowany na inny kanał online.

![Lista witryn w Konstruktorze witryn.](media/channel-mapping-8.png)

## <a name="configure-a-single-domain-name-with-paths-for-multiple-sites"></a>Konfigurowanie jednej nazwy domeny ze ścieżkami dla wielu witryn

Jedna nazwa domeny może być używana dla wielu witryn, a ścieżki mogą być używane do oddzielania witryn lub języków. Na przykład domena `www.mycompany.com` jest skonfigurowana dla dwóch różnych witryn e-commerce: jednej dla firmy Fabrikam i drugiej dla firmy Adventure Works. W tym przypadku domyślna ścieżka (`www.mycompany.com`), znana również jako ścieżka pusta, może być użyta dla witryny Fabrikam, a inna ścieżka (na przykład `www.mycompany.com/adventureworks``) może być użyta dla witryny Adventure Works. Inną opcją jest użycie niestandardowej ścieżki (na przykład `www.mycompany.com/fabrikam`) zamiast domyślnej ścieżki również witryny Fabrikam.

Inną alternatywą jest inna nazwa domeny, która może być używana dla każdej witryny (na przykład w `www.adventure-works.com` i `www.fabrikam.com`). Ścieżki mogą być używane dla różnych języków lub regionów (na przykład `www.adventure-works.com/fr-ca` dla języka francuskiego w Kanadzie).

## <a name="configure-multiple-languages-on-a-site"></a>Konfigurowanie wielu języków w witrynie

Języki można skonfigurować dla witryny sklepu internetowego w programie do budowania witryn pod adresem **Ustawienia witryny \> Kanały**. Na poniższej przykładowej ilustracji każdy język został skonfigurowany przy użyciu ustawień regionalnych ścieżki, tak aby każdy język zawierał unikatowy adres URL.

![W witrynie można skonfigurować wiele języków.](media/channel-mapping-10.png)

Aby dodać nowy język kanału, przejdź do **Ustawienia witryny \> Kanały** i wybierz łącze kanału. W okienku wyświetlanym po prawej stronie wybierz opcję **Dodaj ustawienia lokalne**, aby wybrać kanał i ustawienia lokalne, które chcesz dodać. Następnie określ ścieżkę do użycia dla wybranego kanału.

### <a name="add-and-configure-the-site-picker-module"></a>Dodawanie i konfigurowanie modułu wyboru witryny

Po skonfigurowaniu witryny z wieloma językami i kanałami można dodać selektor języka do nagłówka strony witryny, aby użytkownicy mogli ręcznie wybrać język lub kraj. Moduł nagłówka biblioteki [modułów ma](author-header-module.md) wbudowaną obsługę dla użytkowników, którzy mogą wybrać język za pomocą modułu [selektora witryn](site-selector.md). Moduł wyboru strony można dodać do modułu nagłówka we fragmencie nagłówka.

Aby uzyskać więcej informacji, jak dodać i skonfigurować moduł selektora witryn, zobacz [Moduł selektora witryn](site-selector.md).

### <a name="implement-page-variants-for-each-language"></a>Implementowanie wariantów strony dla każdego języka

W tym scenariuszu jest tylko jeden kanał, ale istnieje wiele języków. Wygląd strony można zmienić w zależności od wybranego języka, tworząc dla niego wariant strony. Następnie możesz dodać zlokalizowany zawartość do wariantu.

Jeśli w Konstruktorze witryn zostanie otwarta strona, a w prawym górnym rogu zostanie wybrane łącze, na którym będzie wyświetlany bieżący kanał i język, pojawi się selektor kanału i języka, tak jak pokazano na poniższej przykładowej ilustracji. Aby zastąpić stronę dla bieżącego języka, wybierz inne ustawienia lokalne, a następnie wybierz pozycję **Zmień**. Kanał można również zmienić, [jeśli zarządzasz witryną, która ma wiele kanałów i języków](#manage-site-content-that has-multiple-channels-and-languages).

![Zmiana języka strony w Konstruktorze witryn.](media/channel-mapping-14.png)

Jeśli wariant dla wybranej strony lub fragmentu nie został jeszcze utworzony, zostanie wyświetlony komunikat ostrzegawczy, jak pokazano na poniższej przykładowej ilustracji. W takim przypadku wybierz łącze **utwórz wariant strony** w tekście komunikatu. Wyświetlane okno dialogowe zawiera opcje, które pozwalają rozpocząć od kopii istniejącego wariantu lub utworzyć nową stronę z szablonu.

![Monituj o utworzenie wariantu strony w Konstruktorze witryn](media/channel-mapping-16.png)

Jeśli wariant nie zostanie wygenerowany, strona oryginalna zostanie wyrenderowana i będzie przedstawiany odpowiedni język dla ciągów modułów i informacji o produkcie z programu Commerce Headquarters. Jeśli jednak tekst, taki jak tytuł strony lub inna zawartość marketingowa, został określony bezpośrednio w domyślnych modułach stron, ciągi dla tego tekstu pozostaną w języku oryginalnym.

Zamiast ręcznie tworzyć poszczególne strony i fragmenty, można eksportować poszczególne strony i fragmenty do pliku XML formatu pliku wymiany (XLIFF), który następnie można wysłać w celu lokalizacji. Po lokalizacji każdego PLIKU XLIFF można zaimportować go jako wariant zlokalizowanej strony. Aby wyeksportować plik XLIFF ze strony lub fragmentu w programie budującym witrynę albo zaimportować plik XLIFF do strony lub fragmentu, wybierz **Lokalizacja** na pasku poleceń. Następnie należy wybrać opcję **Eksportuj XLIFF** lub **Import XLIFF**, tak jak pokazano na poniższej przykładowej ilustracji.

![Importowanie lub eksportowanie strony lub fragmentu w formacie XLIFF.](media/channel-mapping-18.png)

## <a name="manage-site-content-that-has-multiple-channels-and-languages"></a>Zarządzanie zawartością witryny, która ma wiele kanałów i języków

Witryna mająca wiele kanałów i/lub języków przechowuje unikatowy wariant każdej strony i fragmentu dla każdej kombinacji kanału i języka. Takie zachowanie umożliwia tworzenie wariantów stron zawierających zlokalizowane dane, ale również daje elastyczność zmiany wyglądu i działania strony dla określonego wariantu.

Aby uzyskać informacje dotyczące sposobu pracy z wariantami stron, zobacz temat Implementowanie [wariantów strony dla każdej sekcji](#implement-page-variants-for-each-language) językowej tego tematu.

## <a name="configure-multiple-channels-on-an-e-commerce-site"></a>Konfigurowanie wielu kanałów w witrynie e-commerce

Kanały można dodać do witryny handlu elektronicznego w programie do budowania witryn, przechodząc do **Ustawień witryny \> Kanały** i wybierając **Dodaj kanał**. Następnie w wyświetlonym oknie dialogowym **Dodaj kanał** można wybrać kanał internetowy i domyślne ustawienia lokalne.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie kanałów](channels-overview.md)

[Konfigurowanie kanału online](channel-setup-online.md)

[Omówienie organizacji i hierarchii organizacyjnych](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md)

[Konfigurowanie wykrywania i przekierowywania lokalizacji geograficznej](geo-detection-redirection.md)

[Włączanie i używanie udostępniania między kanałami](cross-channel-sharing.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kopiowanie witryny handlu elektronicznego](copy-ecommerce-site.md)

[Moduł selektora witryn](site-selector.md)
