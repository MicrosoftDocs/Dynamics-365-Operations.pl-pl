---
title: Możliwości aplikacji Store Commerce
description: W tym artykule opisano funkcje dostępne w aplikacji Store Commerce dla systemu Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2022-09-30
ms.openlocfilehash: 58f2ab1f913d3629de7971c8eeb2d1821161e44f
ms.sourcegitcommit: 29d9a7573bdac004726da88a9d7b2cc9c383e9ca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2022
ms.locfileid: "9788521"
---
# <a name="store-commerce-app-capabilities"></a>Możliwości aplikacji Store Commerce

[!include [banner](includes/banner.md)]

Aplikacja Store Commerce to nowoczesna aplikacja punktu sprzedaży (POS) dla rozwiązania Microsoft Dynamics 365 Commerce. Dzięki temu firmy mogą przetwarzać transakcje w sklepie i zarządzać operacjami zaplecza, takimi jak zapasy i zamówienia. Aplikacja umożliwia również firmom zarządzanie relacjami z klientami za pomocą programu lojalnościowego i obsługi klientów. 

Zarządzana przez Commerce Scale Unit (CSU) aplikacja Store Commerce stanowi pełne rozwiązanie wielokanałowej. Odbiorca może na przykład kupować produkt w trybie online i odbierać go w sklepie w pobliżu, kontynuując w ten sposób zakupy w różnych kanałach bez utraty żadnych danych. 

Ten artykuł stanowi omówienie możliwości aplikacji Store Commerce.

## <a name="platform"></a>Platforma

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająa |
|---|---|---|---|
| Wielokanałowe | Dynamics 365 Commerce zapewnia kompleksowe rozwiązanie wielokanałowe, które łączy zaplecze biurowe, sklepowe, biura obsługi i cyfrowe. | [Omówienie](index.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/dynamics-365-commerce-overview-november-2-2020) |
| Handel bez kierownictwa | Commerce Scale Unit jest hostem aparatu handlowego bez kierownictwa. Aparat handlu bez kierownictwa pełni rolę punktu centralnego całej logiki biznesowej handlu i oferuje pełne rozwiązanie wielokanałowe. | <p>[Omówienie architektury](commerce-architecture.md)</p><p>[Architektura bez kierownictwa](dev-itpro/retail-server-architecture.md)</p> | [Informacje dotyczące technologii](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-commerce-architecture-overview-december-4-2020) |
| Commerce Headquarters | Program Commerce headquarters oferuje funkcje zaplecza umożliwiające konfigurację produktów, pracowników etatowych, procesów biznesowych, cen i innych funkcji wymaganych przez firmę. | [Omówienie architektury](commerce-architecture.md) | |
| Punkt sprzedaży (POS) | Aplikacja Store Commerce to aplikacja punktu sprzedaży dla systemu Dynamics 365 Commerce. Dostarcza rozbudowane funkcje i rozbudowane funkcje punktu sprzedaży, które pomagają sprzedawcom, kasjerom i menedżerom zapewnić najwyższą obsługę klienta. Ponadto oferuje kilka opcji wdrażania dla sprzedawców detalicznych, pomaga poprawić wydajność i oferuje poprawione zarządzanie cyklem życia aplikacji (ALM). | [Aplikacja Store Commerce](dev-itpro/store-commerce.md) | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/modernize-the-dynamics-365-commerce-in-store-technology-using-the-new-store-commerce-app-march-30-2022)</p><p>[Wideo](https://youtu.be/7B332XH_zfs)</p><p>[Migracja z aplikacji Modern MPOS do sklepu Store Commerce](dev-itpro/pos-extension/migrate-mpos-store-commerce.md)</p> |
| Wdrożenie w chmurze | Dla dystrybucji ładunku i bliskości geograficznej można wdrożyć wiele wystąpień aplikacji Commerce Scale Unit. | [Cloud deployment](../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md) | |
| Wdrożenie lokalne | Korzystając z lokalnego wdrożenia danych biznesowych, klienci Commerce mogą mieć większą własność i zarządzanie środowiskiem systemu Dynamics 365. | [Wdrożenie lokalne](../fin-ops-core/dev-itpro/deployment/deploy-retail-onprem.md) | |

## <a name="device-management"></a>Zarządzanie urządzeniami

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająa |
|---|---|---|---|
| Wiele kształtów | Aplikacja Store Commerce jest obsługiwana przez wiele kształtów urządzenia, takich jak komputery, tablety i urządzenia przenośne. Interfejs użytkownika (UI) umożliwia automatyczne zmienianie rozmiaru układu i korygowanie go zgodnie z rozmiarem ekranu. | [Konfiguracje wizualne](pos-screen-layouts.md) |  |
| Między platformami | Aplikacja Store Commerce jest obsługiwana w sieci web, platformach Windows, iOS i Android. | [Platformy](dev-itpro/hybridapp.md) | |
| Marka | Konstruktor ekranu umożliwia dostosowanie układów ekranu, tak aby spełniały wymagania biznesowe. Oprócz tego na podstawie ról pracowników etatowych można tworzyć motywy, układy, kolory i obrazy, a następnie można je udostępnić innym użytkownikom w celu zachowania spójności marki i ułatwienia ich używania. | [Konfiguracje wizualne](pos-screen-layouts.md) | [Wideo](https://www.youtube.com/watch?v=ldqCw2wf5fY) |
| Topologia | Różne topologie w sklepie są obsługiwane na podstawie dostępności sieci. | <p>[Topologia](dev-itpro/retail-modern-pos-architecture.md)</p><p>[Infografika](dev-itpro/retail-in-store-topology.md)</p> | |
| Zarządzanie wieloma urządzeniami | Z centrali Commerce headquarters można w prosty sposób zarządzać wieloma urządzeniami w różnych sklepach. | [Aktywacja](set-up-activation-accounts-validate-devices-hq.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/commerce-mass-deployment-with-sccm-system-center-configuration-manager-october-6-2022) |

## <a name="employee-management"></a>Zarządzanie pracownikami etatowymi

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająa |
|---|---|---|---|
| Zaloguj się | Każdy pracownik etatowy sklepu może mieć dedykowany podpis. Typy rejestracji to: nazwa użytkownika, kod kreskowy, czytnik kart magnetycznych (MSR), biometryczne i Azure Active Directory (Azure AD). | <p>[Azure AD](aad-pos-logon.md)</p><p>[Logowanie rozszerzone](extended-logon.md)</p> | |
| Uprawnienia | Dla pracowników etatowych są obsługiwane różne poziomy uprawnień, na przykład uprawnienia do tworzenia zamówień i uprawnień do edytowania zamówień. | [Uprawnienia](tasks/create-pos-permission-groups.md) | |
| Zarządzanie czasem i frekwencją | Obecnością można zarządzać przy użyciu funkcji Zegar. Dane dotyczące frekwencji można przetwarzać na listy płac za pomocą aplikacji Dynamics 365 Human Resources. | [Zarządzanie czasem](retail-time-attendance.md) | |
| Prowizja od sprzedaży | Śledzenie sprzedaży realizowanej przez przedstawicieli handlowych może być wykorzystywane do obliczania prowizji i innych premii. | [Prowizja](pos-sales-groups-track-commissions.md) | |

## <a name="merchandising"></a>Działania promocyjne

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająa |
|---|---|---|---|
| Zarządzanie asortymentem | Kierownicy ds. merchandisingu mogą sortować produkty, aby były dostępne do sprzedaży w określonym kanale i w określonym okresie. | [Asortymenty](assortments.md) | |
| Katalogi | Kierownicy ds. merchandisingu mogą zarządzać katalogami w celu określenia produktów, które mają być dostępne po cenie specyficznej dla katalogu. | [Katalogi](/dynamicsax-2012/appuser-itpro/about-retail-product-catalogs) | |
| Zarządzanie produktami i kategoriami | W centrali Commerce headquarters menedżerowie ds. merchandisingu mogą tworzyć produkty, które mają warianty, atrybuty, jednostki miary itp. Mogą również definiować hierarchię kategorii w celu organizowania produktów. | [Produkt](retail-hierarchies.md) | |
| Pakiety | Kierownicy ds. merchandisingu mogą grupować produkty, tak aby były sprzedawane w pakiecie lub zestawie. | [Zestawy](/dynamicsax-2012/appuser-itpro/about-setting-up-retail-product-kits) | |
| Kody informacji | Kodów informacji można użyć do ponaglenia kasjera, aby wprowadzał informacje podczas różnych działań w punkcie sprzedaży, takich jak sprzedaż towaru, zwrot towaru lub wybieranie odbiorców. | [Kody informacji](/dynamicsax-2012/appuser-itpro/about-info-codes-retail) | |
| Połączone towary | Gdy pozycja jest dodawana do transakcji, należy używać pozycji połączonych w celu sprzedaży w górę. | [Połączone towary](/dynamicsax-2012/appuser-itpro/set-up-products-for-cross-selling-and-up-selling) | |
| Gwarancje | Rozszerzone gwarancje można sprzedawać razem z produktami. | [Gwarancja](extended-warranty.md) | |
| Drukowanie etykiet | Etykiety można generować, by zawierały takie informacje o produktach, jak numer partii, numer seryjny i data ważności. | [Drukowanie etykiet](/dynamicsax-2012/appuser-itpro/create-and-print-labels-overview) | |

## <a name="assisted-selling"></a>Sprzedaż wspomagana

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająa |
|---|---|---|---|
| Przeglądanie produktów | Przeglądaj produkty według kategorii. | [Hierarchia produktów](retail-hierarchies.md) | |
| Wyszukiwanie produktu | Wyszukuj produkty według nazw i zawężaj wyszukiwanie, używając atrybutów produktów, takich jak marka, cena czy materiały. Ta funkcja jest zasilana przez usługę Azure Cognitive Search. | [Zaawansowane wyszukiwanie w chmurze](cloud-powered-search-overview.md) | |
| Strona Szczegóły produktu | Strony szczegółów produktów sformatowanych mogą zawierać obrazy, opis, atrybuty produktu i zalecane produkty. Rekomendacje są obsługiwane przez usługę Rekomendacje. | | |
| Porównanie produktów | Porównanie wielu produktów i pomaganie klientom w ich wybraniu i dodaniu do transakcji. | | |
| Nieskończone przejście | Można łatwo szukać zapasów w innych sklepach i tworzyć zamówienia. | [Wyszukiwanie w magazynie](pos-inventory-lookup-operation.md) | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |
| Rekomendacje | Produkty w sprzedaży do góry i równoległej za pomocą usługi Rekomendacje. Ta usługa używa technologii patentowanej do proponowania rekomendacji na podstawie trendów zakupów oraz cech, takich jak nowości, podobny wygląd i najpopularniejsze. Te rekomendacje są dostępne na stronach szczegółów produktu, stronach **Szczegóły odbiorcy** i **Transakcje**. | [Rekomendacje](product-recommendations.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-recommendations-march-2-2021) |

## <a name="customer-relationship"></a>Relacja odbiorcy

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająa |
|---|---|---|---|
| Zarządzanie klientami | Twórz, edytuj i zarządzaj kontami klientów. Kontami klientów można zarządzać w trybie asynchronicznym, aby uniknąć przetwarzania w czasie rzeczywistym. | [Zarządzanie](customer-mgmt-stores.md) | |
| Atrybuty klienta | Struktura atrybutów odbiorcy umożliwia przechwytywanie dodatkowych danych związanych z klientem na podstawie wymagań biznesowych. | [Atrybuty](dev-itpro/customer-attributes.md) | |
| Strona szczegółów na temat klienta | Strona rozbudowanych szczegółów dotyczących klienta umożliwia wyświetlenie widoku kanału informacji o interakcjach odbiorcy we wszystkich kanałach. Te interakcje obejmują zakupy, listy życzeń i punkty lojalnościowe. | | |
| Omówienie wyszukiwania odbiorców | Wyszukaj odbiorców według nazwiska, numeru telefonu, adresu e-mail, karty lojalnościowej, adresu itp. | [Zaawansowane wyszukiwanie w chmurze](pos-search-improvements.md#customer-search) | |
| Nagrody i program lojalnościowy | Odbiorcy mogą przystąpić do programów lojalnościowych oraz uzyskać i zrealizować punkty lojalnościowe w różnych kanałach. | [Lojalność](set-up-customer-loyalty-program.md) | [Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5c2wW) |
| Obsługa relacji z klientami | Zarządzanie głównymi klientami przy użyciu księgi klienta oraz śledzić działania i notatki w profilu odbiorcy. Integracja Dynamics 365 Customer Insights umożliwia pracowników sklepu mogą uzyskać informacje o następnej najlepszej akcji dla każdego odbiorcy. | [Obsługa relacji z klientami](clienteling-overview.md#activities-and-notes) | [Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSP) |

## <a name="pricing-and-discounts"></a>Ceny i rabaty

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Umowy handlowe | Menedżerowie cen mogą używać umów handlowych do określania cen specjalnych na podstawie umów długoterminowych dotyczących określonych odbiorców. | [Ceny](price-management.md)| [Wideo](https://www.youtube.com/watch?v=r2VD8IxHesM) |
| Umowy sprzedaży | Menedżerowie cen mogą używać umów sprzedaży do definiowania cen opartych na kontrakcie w scenariuszach handlu między firmami (B2B). | [Ceny](price-management.md) | |
| Korekty ceny | Menedżerowie cen mogą używać możliwości korekty ceny do tworzenia, śledzenia i zarządzania obniżkami cen swoich produktów wraz z upływem czasu. | [Korekty ceny](price-adjustments-discounts.md) | |
| Rabaty | Menedżerowie cen mogą skonfigurować kilka typów rabatów, aby uruchamiać różne promocje. Te rabaty zawierają proste rabaty, rabaty ilościowe, rabaty progowe, rabaty łączone i rabaty ręczne, rabaty oparte na formach płatności i wysyłkowe. | [Rabaty](retail-discounts-overview.md) | |
| Kupony | Menedżerowie cen mogą ustawiać kody kuponów lub kody kreskowe, łączyć je z rabatami i dystrybuować do odbiorców. Sprzedawcy mogą dodawać kupony do transakcji sprzedaży lub je usuwać. | [Kupony](coupons.md) | |
| Grupy cenowe | Menedżerowie cen mogą używać funkcji grupy cenowej do definiowania cen kontekstowych na podstawie kanałów, katalogów, przynależności lub programów lojalnościowych. | [Ceny](price-management.md) | |
| Dostępne promocje | Sprzedawcy mogą łatwo szukać dostępnych promocji dla produktów w sklepie, produktów dodanych do transakcji itp. | [Funkcje cen](pos-pricing-functions.md) | |
| Operacje sprawdzania ceny | Sprzedawcy mogą szybko sprawdzać aktywne ceny sprzedaży produktów w sklepie. | [Funkcje cen](pos-pricing-functions.md) | |
| Zastąpienia ceny | Sprzedawcy, którzy mają wymagane uprawnienia, mogą zastępować ceny skonfigurowane przez system lub obliczone. | [Funkcje cen](pos-pricing-functions.md) | |
| Rabaty ręczne | Sprzedawcy, którzy mają wymagane uprawnienia, mogą stosować rabaty ręczne do transakcji sprzedaży lub wierszy sprzedaży. | [Funkcje cen](pos-pricing-functions.md) | |

## <a name="electronic-payments"></a>Płatności elektroniczne

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Kredytowe i debetowe | Aplikacja Store Commerce obsługuje główne płatności kartą kredytową i debetową za pośrednictwem bramy płatności Adyen oraz realizacji zamówień za pośrednictwem usługi PayPal. Zestaw SDK płatności umożliwia korzystanie z połączeń bramy zewnętrznej, które są obsługiwane przez integracje niezależnych dostawców oprogramowania (ISV). | <p>[Adyen](dev-itpro/adyen-connector.md?tabs=10-0-23)</p><p>[PayPal](paypal.md)</p><p>[Płatności](payment-methods.md)</p> | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-configuration-february-9-2021)</p><p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-overview-processing-february-4-2021)</p> |
| Obsługa płatności dokonywanych za pomocą portfeli | Aplikacja Store Commerce obsługuje płatności za pomocą form płatności portfeli cyfrowych, w których nie są stosowane zakresy numeru identyfikacyjnego banku (BIN) jak w przypadku tradycyjnych kart kredytowych i debetowych. Formy płatności mogą być mapowane na płatności cyfrowe, takie jak Adyen. | [Portfel](wallets.md) | |
| Obsługa kart upominkowych | Numer identyfikacyjny banku karty upominkowej Dynamics 365, przechowywane rozwiązania wartości (SVS) i karty upominkowe Givex. Karty upominkowe można kupować i zrealizować w zamówieniu. | [Karty upominkowe](dev-itpro/gift-card.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/d365-commerce-internal-gift-cards-november-16-2021) |
| Ochrona przed oszustwami | Dynamics 365 Fraud Protection pomaga zapobiec fałszywym działaniom i identyfikować miejsca, w których oszustwa mogą być niezauważone. | [Ochrona przed oszustwami](dev-itpro/dfp.md) | [Wideo](https://www.youtube.com/watch?v=j_1nEiq3LfM) |

## <a name="taxes-and-charges"></a>Podatki i opłaty

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Podatki | Aplikacja Store Commerce obsługuje wiele różnych rodzajów podatków pośrednich, takich jak podatek, podatek od wartości dodanej (VAT), podatek od towarów i usług (GST), opłaty oparte na jednostce i potrącona zaliczka na podatek. | [Podatki](/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json) | |
| Opłaty | Opłaty można konfigurować na poziomie wiersza, na poziomie nagłówka, jako opłaty automatyczne, według kanału itp. | [Opłaty](omni-auto-charges.md) | |

## <a name="order-processing-and-fulfillment"></a>Przetwarzanie i realizacja zamówienia

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Tworzenie zamówienia | Zamówienie można utworzyć w celu wysyłki lub pobrania w pobliskim sklepie. Dla pobrania można określić przedziały czasowe. | [Omówienie](customer-orders-overview.md) | |
| Modyfikacja zamówienia | Zamówienie może być modyfikowane, zwracane, anulowane itp. | <p>[Anuluj](customer-orders-overview.md#cancel-a-customer-order)</p><p>[Zwroty](pos-returns.md)</p> | |
| Wyszukiwanie | Wyszukiwanie i filtrowanie zamówień przy użyciu informacji specyficznych dla zamówienia. | [Wyszukiwanie](enhancedorderrecall.md) | |
| Atrybuty zamówienia | Struktura atrybutów zamówienia umożliwia przechwytywanie dodatkowych danych związanych z zamówieniem na podstawie wymagań biznesowych. | [Atrybuty](dev-itpro/order-attributes.md) | |
| Dostawa bezpośrednia | Towary mogą być oznaczone przez dostawcę do dostawy bezpośredniej pod adres odbiorcy. Jest to dostawa bezpośrednia. | [Dostawa bezpośrednia](/dynamics365/supply-chain/sales-marketing/tasks/ship-orders-direct-deliveries) | |
| Oferta | Pracownicy etatowi sklepu mogą tworzyć oferty dla odbiorców oraz określać specjalną cenę, ręczne rabaty i datę ważności oferty. | [Oferta](/dynamics365/supply-chain/sales-marketing/tasks/create-edit-sales-quotations) | |
| Realizacja | Sklepy mogą odbierać, pakować i wysyłać zamówienia. Do paczek gotowych do wysyłki można dodać dokument dostawy. | [Realizacja](order-fulfillment-overview.md) | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-supporting-buy-online-pickup-in-store-curbside-with-dynamics-365-commerce-pos-february-3-2021)</p> <p>[Wideo](https://www.microsoft.com/videoplayer/embed/RE5bRXE)</p>|
| Zarządzanie zamówieniami rozdzielonymi | Aplikacja Store Commerce obsługuje inteligentną optymalizację realizacji zamówień, w której można konfigurować strategie biznesowe w oparciu o charakter firmy, typ odbiorcy, pochodzenie zamówienia i metodę dostawy dla zamówienia. | [DOM](dom.md) | [Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bRYl)|

## <a name="inventory-management"></a>Zarządzanie zapasami

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Dystrybucja na zamówienie | Usprawnij dystrybucję dostępnych zapasów z centrum dystrybucji do wielu sklepów lub magazynów. | [Dystrybucja na zamówienie](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Przeładunek kompletacyjny | Usprawnij dystrybucję zapasów w przychodzących zamówieniach zakupu do wielu sklepów lub magazynów. | [Przeładunek kompletacyjny](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Zapasy przychodzące | Odbieraj zapasy od dostawcy za pośrednictwem zamówienia zakupu lub z innego magazynu za pośrednictwem zamówienia przeniesienia. Tworzenie przychodzącego zamówienia zakupu lub żądania zamówienia przeniesienia. | [Przychodzące](pos-inbound-inventory-operation.md) | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p>  <p>[Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p>|
| Zapasy wychodzące | Wysyłaj zapasy do innego magazynu za pośrednictwem zamówienia przeniesienia i twórz żądanie wychodzącego zamówienia przeniesienia. | [Wychodzące](pos-outbound-inventory-operation.md) | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p>  <p>[Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |
| Wyszukiwanie w magazynie | Sprawdź dostępne zapasy produktów w sklepach i magazynach i sprawdź dostępne zapasy (ATP) w przyszłych datach. | [Wyszukiwanie w magazynie](pos-inventory-lookup-operation.md) | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |
| Korekta zapasów | Korygowanie zapasów w lub poza magazynem sklepu w celu spełnienia określonych wymagań biznesowych bez używania sprzedaży, przychodu ani ponownego konta. | [Korekta zapasów](work-with-store-inventory.md) | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p>|
| Stany zapasów z inwentaryzacji | Zlicz zapas fizyczny i dostosuj systemowy zapas księgowy, tak aby był do niego dopasowany. | [Inwentaryzacja](work-with-store-inventory.md) | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)<p> |
| Przesunięcie magazynowe | Przenoszenie zapasów między lokalizacjami w sklepie. | [Przeniesienie](work-with-store-inventory.md) | <p>[Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Wideo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |

## <a name="financials"></a>Finanse

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Zarządzanie gotówką | Aplikacja Store Commerce obsługuje zarządzanie gotówką i innymi określonymi płatnościami w sklepie. Ponadto uzgodnienie zmian w sklepie można włączyć dla zaawansowanych możliwości zarządzania gotówką. | [Kasa](cash-mgmt.md) | |
| Zestawienia finansowe i uzgodnienie | Transakcje kasowe i transakcyjne dla sklepu są rejestrowane w programie Commerce Headquarters za pośrednictwem procesów księgowania zestawienia. | [Zestawienia](retail-statements.md) | |
| Transakcje przychodów i wydatków | Przetwarzanie transakcji gotówkowych w sklepie i rejestrowanie przychodów, które nie pochodzą z tradycyjnego sposobu, takich jak pieniądze utracone i znalezione, udział przychodu z kawiarni w holu, czy usługi czyszczenia dywanów. | [Zestawienia](retail-statements.md) | |
| Płatności faktury | Przechwytywanie płatności względem faktur. | [Faktura VAT](payinvoice.md) | |

## <a name="employee-productivity"></a>Produktywność pracowników etatowych

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Zarządzanie zadaniami | Umożliwia tworzenie list zadań i zadań oraz przypisywanie ich do sklepów i pracowników etatowych. Śledź stan zadań w różnych sklepach. Zapewnia bezproblemową integrację z aplikacją Microsoft Teams. | <p>[Zarządzanie zadaniami](task-mgmt-overview.md)</p><p>[Microsoft Teams](commerce-teams-integration.md)</p> | [Wideo](https://www.youtube.com/watch?v=ES1whB4C2lU) |

## <a name="hardware-and-peripherals"></a>Sprzęt i urządzenia peryferyjne

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Podłączanie urządzeń peryferyjnych | Łączenie urządzeń zewnętrznych, takich jak drukarki, szuflady kasowe, skanery, czy urządzenia płatności z terminalem punktu sprzedaży. | [Urządzenia peryferyjne](retail-peripherals-overview.md) ||
| Udostępnianie urządzeń peryferyjnych | Drukarki paragonów, szuflady kasowe i urządzenia płatnicze można udostępnić wielu terminalom, podłączając je do wspólnej stacji sprzętowej. | <p>[Stacja sprzętowa](retail-peripherals-overview.md) ||
| Symulator punktu sprzedaży i urządzeń peryferyjnych | Symulator urządzeń peryferyjnych służy do testowania scenariuszy, w których zazwyczaj wymagane jest używanie fizycznych urządzeń peryferyjnych punktu sprzedaży. Zawiera także symulator punktu sprzedaży, który umożliwia testowanie zgodności fizycznych urządzeń peryferyjnych bez wdrażania klienta punktu sprzedaży. | [Symulator](dev-itpro/retail-peripheral-simulator.md) | |

## <a name="receipts"></a>Odbiory

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Drukuj paragony | Dokumenty sprzedaży różnych typów, takie jak paragony sprzedaży, paragony kart kredytowych, paragony upominkowe i faktury, mogą być drukowane domyślnie lub po potwierdzeniu kasjera podczas realizacji zamówienia. Można je także ponownie wydrukować z arkusza. | [Drukowanie](receipt-templates-printing.md) | |
| Paragony w wiadomościach e-mail | Po zakończeniu realizacji zamówienia można wysłać paragony z punktu sprzedaży. | [Wiadomość e-mail](email-receipts.md) | |
| Projektowanie pokwitowań | Paragony w sklepie można dostosowywać, tak aby były wyświetlane dane i układy odpowiednie do potrzeb sprzedawcy detalicznego i typu transakcji. Paragony można również rozszerzać, aby wyświetlać niestandardowe dane wymagane przez sprzedawcę detalicznego. | [Projekt](receipt-templates-printing.md) | |

## <a name="offline-support"></a>Obsługa trybu offline

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Bezproblemowy tryb offline | Bezproblemowa łączność w trybie offline umożliwia kontynuację transakcji, nawet jeśli łączność internetowa jest ograniczona lub nie jest dostępna. Wykluczenie danych pomaga redukować rozmiar danych bazy danych offline i maksymalizować wydajność. | [Offline](pos-operations.md) | |
| Przełączanie oparte na wydajności | Przełącz się do trybu offline po wykryciu obniżenia wydajności. | [Offline](dev-itpro/implementation-considerations-offline.md) | [Wideo](https://youtu.be/sQU-2pgHToI) |
| Pulpit nawigacyjny trybu offline | Na pulpicie nawigacyjnym **Stan offline** są dostępne informacje o stanie offline, błędach i szczegółach danych poszczególnych urządzeń. Dzięki temu zarządzanie stanem wielu urządzeń jest proste. | [Offline](dev-itpro/implementation-considerations-offline.md) | [Wideo](https://youtu.be/sQU-2pgHToI)|

## <a name="extensibility"></a>Możliwości rozszerzania

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Commerce Headquarters | Rozwiązania w centrali Commerce headquarters można dostosowywać, dodając lub modyfikując procesy biznesowe. Program Commerce headquarters obsługuje używanie metadanych i modelu rozszerzeń opartych na kodzie w celu dodawania niestandardowych funkcji. Można go łatwo zintegrować z rozwiązaniami zewnętrznymi. | [Omówienie](dev-itpro/extend-customer-cdx-package.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-unlock-the-power-of-dynamics-365-commerce-commerce-extensibility-overview-february-23-2021) |
| Handel bez kierownictwa | W celu dostosowania i dodania logiki biznesowej można użyć rozszerzalnej struktury wielokanałowego interfejsu API. Interfejsy API, które mają programy obsługi żądań, oraz wzorce rozszerzeń przed i po wyzwoleniu. | [CSU](dev-itpro/retail-server-customer-consumer-api.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Zestaw SDK do Commerce | Zestaw SDK do Commerce zawiera kod, przykłady kodów, szablony i narzędzia wymagane do rozszerzania lub dostosowywania funkcjonalności Dynamics 365 Commerce. Zestaw SDK jest publikowany w różnych repozytoriach (repo) w GitHub w zależności od składników rozszerzenia. | [Zestaw SDK](dev-itpro/retail-sdk/sdk-github.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Punkt sprzedaży | Aplikacja Store Commerce można rozszerzać niezależnie, używając funkcji rozszerzenia punktu sprzedaży zestawu SDK do Commerce. Struktura obsługuje dostosowanie interfejsu użytkownika (UX), przepływów pracy i logiki biznesowej. | [Punkt sprzedaży](dev-itpro/pos-extension/pos-extension-overview.md) | [Informacje dotyczące technologii](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |

## <a name="reporting"></a>Raportowanie

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Raporty sprzedaży | Raporty sprzedaży według pracowników, rejestru, typu płatności, zwrotów, produktów itp. są dostępne dla menedżerów sklepów. Menedżerowie mogą przeglądać te raporty i używać ich do przydzielania prowizji i identyfikowania trendów produktów. | | |

## <a name="diagnostics"></a>Diagnostyka

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Operational Insights | W subskrypcji odbiorcy Application Insights są dostępne dane o niezawodności i wydajności przechowywanej w sklepie. Dostępne są zaawansowane funkcje alertów i monitorowania. | | |
| Sprawdzanie kondycji | Uruchamiając operację sprawdzania kondycji, można sprawdzić dostępność urządzeń peryferyjnych połączonych z punktem sprzedaży. Następnie można naprawić i zweryfikować poszczególne problemy peryferyjne. | [Sprawdzanie kondycji](pos-healthcheck.md) | [Wideo](https://www.youtube.com/watch?v=RfPDNmnqYvY) |

## <a name="globalization"></a>Globalizacja

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Obsługa wielu rynków | Dostępne na rynku funkcje, takie jak integracja fiskalna, podatek GST, zaawansowane fakturowanie i przedpłaty, są obecnie obsługiwane. Te możliwości obejmują kilka rynków w Europie, Amerykach, Rosji, Azji, Arabii Saudyjskiej itp. | [Globalizacja](localizations/fiscal-integration-for-retail-channel.md) | |

## <a name="compliance"></a>Zgodność

| Możliwość | Opis | Dokumentacja | Zawartość uzupełniająca |
|---|---|---|---|
| Standardy firmy Microsoft | Aplikacja Store Commerce spełnia standardy firmy Microsoft dotyczące zabezpieczeń, prywatności, ułatwień dostępu, Ogólnego rozporządzenia o ochronie danych (RODO), granicy danych Unii Europejskiej (UE) itp. | | |

