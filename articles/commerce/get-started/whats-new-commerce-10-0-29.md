---
title: Wersja zapoznawcza aplikacji Dynamics 365 Commerce 10.0.29 (październik 2022 r.)
description: W tym artykule opisano nowe oraz zmienione funkcje dostępne w Microsoft Dynamics 365 Commerce 10.0.29.
author: josaw1
ms.date: 08/02/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c1f85fcd8f79106a3af93489d3bef608b9840bf3
ms.sourcegitcommit: 91f58a9863f4e8f30ac787c2a9771c1ff6a05f72
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224246"
---
# <a name="preview-of-dynamics-365-commerce-10029-october-2022"></a>Wersja zapoznawcza aplikacji Dynamics 365 Commerce 10.0.29 (październik 2022 r.)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Commerce w wersji zapoznawczej w wersji 10.0.29. Ta wersja ma numer kompilacji 10.0.1326 i jest dostępna w następującym harmonogramie:

- **Wersja zapoznawcza wydania:** sierpień 2022 r.
- **Ogólna dostępność wydania (samodzielna aktualizacja):** wrzesień 2022 r.
- **Ogólna dostępność wydania (samodzielna aktualizacja):** październik 2022 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Możemy zaktualizować ten artykuł, aby uwzględnić cechy, które zostały dodane do kompilacji po opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---------|------------------|----------------|--------------| 
| B2B | [Włącz obsługę umów sprzedaży w wielu kanałach](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-b2b-sales-agreement-contract-based-pricing) | Ta funkcja umożliwia organizacjom sprzedającym między firmami (B2B) korzystanie z umów sprzedaży w programie Commerce Headquarters w celu określania cen na podstawie umowy dla ich kupców. Gdy sklep typu B2B w witrynie sieci web portalu e-commerce zawiera informacje, ceny na podstawie umowy skonfigurowane dla organizacji kupca B2B są automatycznie stosowane w odniesieniu do całego doświadczenia w zakresie wykrywania produktów, zakupu i realizacji zamówienia. | Zarządzanie funkcjami<p>*Obsługa umowy sprzedaży między kanałami handlowymi* |
| Customer Service | [Włączanie obsługi klienta za pomocą usługi Dynamics 365 Obsługa wielokanałowa dla Customer Service](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/chat-dynamics-365-commerce-omnichannel-customer-service) | Najwyższej klasy obsługa klienta jest kluczem do zapewnienia konsumentom spersonalizowanych i zachwycających doświadczeń handlowych. Obecnie istnieje wiele punktów kontaktowych commerce, takich jak sklepy fizyczne, kanały online i kanały społecznościowy. Klienci oczekują spersonalizowanej obsługi we wszystkich tych punktach kontaktowych. Ta funkcja pomaga zwiększyć konwersje koszyków na sprzedaż, zwiększyć spersonalizowaną relację z klientami i usprawnić obsługę klienta, integrując z usługami Dynamics 365 Obsługa wielokanałowa dla Customer Service. | Włączone przez administratorów/administratorów |
| Handel elektroniczny | Obsługa porównania produktów w handlu elektronicznym | Umożliwia użytkownikom porównywanie produktów z różnych kategorii, dzięki czemu mogą sami podjąć właściwą decyzję o zakupie. Ta funkcja jest dostępna zarówno dla witryn B2C (business-to-consumer), jak i B2B. | Konstruktor witryn. | 
| Karty upominkowe | Obsługa tabel kart upominkowych sieci sprzedaży do udostępniania danych między firmami | Centrala systemu Dynamics obsługuje funkcję udostępniania danych między firmami dla określonych tabel w architekturze systemu Dynamics. W tej funkcji Dynamics 365 Commerce dodaje obsługę udostępniania danych między firmami dla tabel kart podarunkowych sieci sprzedaży. Dlatego karta upominkowa w jednej firmie może teraz mieć zduplikowane dane w środowisku dla innej firmy. Zmiany wprowadzone w tabeli karty upominkowej firmy inicjatora zostaną udostępnione w tabeli zduplikowanych firmowych kart upominkowych. | Deweloperzy |
| Wydajność | Usuń zależność rts dla scenariuszy „edycji odbiorcy” | Wysoka dostępność i wysoka wydajność to domyślne oczekiwania wobec kanałów w punkt sprzedaży (POS) i kanałów w handlu e-commerce. Aby spełnić te oczekiwania, podczas edytowania informacji o odbiorcy kanały Dynamics 365 Commerce nie muszą już liczyć się z komunikacją w czasie rzeczywistym z Commerce headquarters. Możliwość asynchronicznej edycji informacji o odbiorcy w przypadku odbiorców asynchronicznych i niesynchronicznie może pomóc w redukowania wywołań w czasie rzeczywistym w Commerce headquarters. | Włączone przez administratorów/administratorów |

## <a name="feature-state-changes-in-this-release"></a>Zmiany w stanie funkcji w tym wydaniu

Poniższa tabela zawiera listę cech, które stały się obowiązkowe lub domyślnie włączone począwszy od 10.0.29. Wszystkie te funkcje zostaną automatycznie włączone w twoim systemie, gdy tylko zaktualizujesz go do wersji 10.0.29. Nie można wyłączyć funkcji obowiązkowych, ale funkcje, które są domyślnie włączone, mogą być nadal wyłączone za pomocą funkcji [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

W tabeli wymieniono również funkcje, które wcześniej były dostępne w publicznej wersji zapoznawczej, ale zostały zmienione i stały się ogólnie dostępne w wersji 10.0.29. Ta zmiana wskazuje, że funkcje są teraz zalecane do użycia w środowiskach produkcyjnych. Te funkcje są domyślnie wyłączone, chyba że zaznaczono inaczej. Dlatego musisz użyć [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby je włączyć, jeśli chcesz Użyj ich.

| Funkcja | Tytuł | Nowy stan funkcji |
| --- | --- | --- |
| BrazilRetailLocalizationFeature_BR |(Brazylia) Funkcje aplikacji Commerce właściwe dla Brazylii | Domyślnie włączona |
| RetailAdvancedGTETaxAdjustmentFeature | (Indie) Zastosuj podatek GST obliczony dla transakcji sprzedaży detalicznej w module Retail POS do zestawień sprzedaży detalicznej | Domyślnie włączona |
| RetailChronologicalInvoicePostingFeature_IT | (Włochy) Włącz księgowane faktury sieci sprzedaży bez porządku chronologicznego | Domyślnie włączona |
| RetailDiscountWithoutTaxAdjustingFeature_MX | (Meksyk) Korekta rabatu w globalnym handlu detalicznym CFDI | Domyślnie włączona |
| RetailFiscalIntegrationConfigurationEnhancementFeature | Zastąpienia technicznego profilu integracji fiskalnej | Domyślnie włączona |
| RetailFiscalIntegrationConnectorLocationFeature | Bezpośrednia integracja fiskalna z kas punktów sprzedaży | Domyślnie włączona |
| RetailFiscalIntegrationLocalStorageBackupEnableFeature | Kopia zapasowa magazynu lokalnego integracji fiskalnej | Domyślnie włączona |
| RetailFiscalIntegrationPostponeFiscalRegistrationFeature | Odroczona rejestracja dokumentów | Domyślnie włączona |
| RetailFiscalIntegrationRegistrationProcessTerminalExceptionFeature | Stan rejestracji fiskalnej kas punktów sprzedaży | Domyślnie włączona |
| RetailGSTInvoiceAddressTaxCalculationFeature_IN | (Indie) Obliczanie podatku GST na podstawie adresu faktury dla zamówień handlu elektronicznego | Domyślnie włączona |
| RetailInvoicesDefaultSalesDocumentStatusFeature_PL | (Polska) Domyślny stan dokumentu sprzedaży dla faktur sieci sprzedaży | Domyślnie włączona |
| RetailRecalculateRoundingOfTaxBaseAmountsFeature_MX | (Meksyk) Ponowne obliczenie zaokrągleń kwot podstawy podatku w module globalnym CFDI usługi Retail. | Domyślnie włączona |
| RetailSupplementaryInvoiceFeature | Włącz faktury uzupełniające dla transakcji gotówkowych i przenoszenia wypełnione w sklepach detalicznych | Domyślnie włączona |
| RetailInventoryBufferAndInventoryLevelEnableFeature   |  Włącz bufor zapasów i poziomy zapasów    |  Domyślnie włączona|
|RetailInboundOutboundInventoryValidationFeature|   Włącz weryfikację operacji zapasów przychodzących i wychodzących w punkcie sprzedaży   |   Domyślnie włączona   |
|  RetailInventoryChannelCalculationConsolidationFeature    |  Rozszerzona logika obliczania zapasów po stronie kanału handlu elektronicznego |   Domyślnie włączona   |
|RetailInventoryAdjustmentsInPointOfSaleFeature|    Korekty zapasów w punkcie sprzedaży   |  Domyślnie włączona  |
| RetailMultiplePickupDeliveryModeFeature |  Obsługa wielu metod pobrania dostawy     |   Wymagana    |
|  RetailProductAvailabilityOptimizationFeature |   Zoptymalizowane obliczanie dostępności produktu  |  Wymagana |
|   RetailPricingDataManagerV2Feature   |   Zwiększ wydajność aparatu cenowego rozwiązania Commerce |   Wymagana |
|  RetailPricingPreventUnintendedRecalculationFeature   | Zapobiegaj niekontrolowanemu obliczaniu cen dla zamówień handlowych    |  Wymagana  |
| RetailTeamsIntegration    |   Włącz integrację z programem Microsoft Teams| Wymagana   |  
| ConsumerEFDSyncProcessFeature_BR | (Brazylia) Przetwarzanie synchroniczne NFC-e | Domyślnie włączona |
| RetailFiscalIntegrationInternalAndExternalServicesEnableFeature | Obsługa wewnętrznych i zewnętrznych łączników w strukturze integracji fiskalnej | Wymagana |
| RetailTaxRegistrationIdEnableFeature_BR | (Brazylia) Wyszukaj odbiorców w programie Retail POS według numerów identyfikacji podatkowej | Wymagana |
| RetailTaxRegistrationIdEnableFeature_IN | (Indie) Wyszukaj odbiorców w programie Retail POS według numerów identyfikacji podatkowej | Wymagana |
| RetailTaxRegistrationIdEnableFeature_IT | (Włochy) Zarządzanie informacjami o odbiorcach w programie Retail POS | Wymagana |
| RetailTaxRegistrationIdEnableFeature_PL | (Polska) Zarządzanie informacjami o odbiorcach w programie Retail POS | Wymagana |
| RetailUpdateReturnOriginalTransactionIdGlobalEnableFeature_IN | (Podatek GST od sprzedaży detalicznej w Indiach) Aktualizuj faktury korygujące o odwołania do oryginalnych faktur | Wymagana |
| RetailUserDefinedCertificateProfileFeature | Profile certyfikatów zdefiniowane przez użytkownika dla sklepów detalicznych | Wymagana |
  

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji Finanse i Działania

Microsoft Dynamics 365 Commerce 10.0.29 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.29 aplikacji Finanse i Działania (październik 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md). 

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.29, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559&dbType=3&qc=ec3e3846199f5d3a27a0c4949e3902ffdbc87560f0cf928c4838b3bdd421633c). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2022 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2022 r.](/dynamics365-release-plan/2022wave2/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-features"></a>Usunięte i wycofane funkcje

Artykuł [Usunięte lub wycofane funkcje w Dynamics 365 Commerce](removed-deprecated-features-commerce.md) opisuje funkcje, które zostały usunięte lub przestarzałe dla handlu.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji artykułu na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
