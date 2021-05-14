---
title: Fakturowanie elektroniczne — FAQ
description: Ten temat zawiera informacje dotyczące często zadawanych pytań dotyczących fakturowania elektronicznego.
author: gionoder
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 2efad243044304b895726ab763fd3744282abd16
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935640"
---
# <a name="electronic-invoicing-faq"></a>Fakturowanie elektroniczne — często zadawane pytania

[!include [banner](../includes/banner.md)]

Ten temat zawiera odpowiedzi dotyczące często zadawanych pytań dotyczących usługi fakturowania elektronicznego. Fakturowanie elektroniczne rozszerza możliwości fakturowania elektronicznego istniejące w Dynamics 365 Finance, Dynamics 365 Supply Chain Management i Dynamics 365 Project Operations. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>Co jest istotne dla fakturowania elektronicznego i dlaczego ma to znaczenie dla mojej organizacji?

Złożoność operacyjna i ryzyko nadal wzrastają globalnie w miarę wzrostu organizacji i rozszerzania ich organizacji w różnych regionach. Zachowywanie zgodności z przepisami i dostosowywanie się do często zmienianych przepisów stanowi problem i ma szczególne znaczenie podczas fakturowania. Fakturowanie jest zwykle kosztowne i często związane z błędami, ponieważ firmy korzystają z dokumentów papierowych i ręcznie przetwarzają wiele procesów.  

Organizacje zostały rozpoczęte, aby odejść od faktur papierowych, aby zmniejszyć koszty i przyspieszyć proces zakończenia produkcji. Rządy kojarzeją się z fakturowaniem elektronicznym jako głównym składnikiem globalizacji podatków. Wymaganie od organizacji przesyłania cyfrowo informacji podatkowych w czasie rzeczywistym do urzędów skarbowych, rządy mogą zminimalizować liczbę podatków związanych z podatkami i ich redukowanie oraz redukować oszustwa. 

Na świecie zmienia się elektroniczny proces przetwarzania dokumentów i bez implementowania fakturowania elektronicznego odbiorcy mogą ryzykować problemami z zgodnością, zbędne koszty i opóźniać się w przypadku konkurentów. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>Czy funkcje fakturowania elektronicznego nie są już dostępne w funkcjach Finance, Supply Chain Management i Project Operations? Jaka wartość dostarcza mi jako odbiorca? 

Fakturowanie elektroniczne rozszerza możliwości fakturowania elektronicznego, które istnieją w Finance, Supply Chain Management i Project Operations. Upraszcza ono również zgodność z najnowszymi standardami fakturowania elektronicznego i umożliwia obsługę różnych regionów w przetwarzaniu i wymianie elektronicznej. Możliwości fakturowania elektronicznego odblokują szereg świadczeń, w tym: 

   - Szybsze i łatwe przyjęcie wymagań specyficznych dla kraju/regionu.
   - Standardizacja implementacji rozwiązań fakturowania elektronicznego. 
   - Rozszerzone możliwości śledzenia przetwarzania faktur e-mail.  
   - Łatwiejsza obsługa w celu zachowania zgodności ze prawnymi wymaganiami i lokalnymi praktykami biznesowymi. 
   - Uproszczone opakowanie rozwiązania.
   - Możliwości skalowania dla dużej liczby przesłanych dokumentów skutkują szybszym obrotem.
   - Możliwość udostępniania rozwiązań innym firmom.

## <a name="does-electronic-invoicing-service-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>Czy usługa fakturowania elektronicznego obsługuje lokalne instalacje Finance, Supply Chain Management i Project Operations? 

Bieżąca platforma nie zezwala na używanie lokalnej wersji i nie ma planów, aby ją obsługiwać w przyszłości.

## <a name="does-electronic-invoicing-service-interface-with-the-vendor-import-automation-feature"></a>Czy interfejs usługi fakturowania elektronicznego z funkcją automatyzacji importu dostawców?

Nr Istnieją plany dla tego interfejsu, ale nie zaplanowano osi czasu. Jeśli to planowane, daty będą się dzieje w [Planach zwalniania](/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-service-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>W jaki sposób usługa fakturowania elektronicznego obsługuje załączniki plików do faktury elektronicznej? Czy serwer SharePoint jest potrzebny do osadzania plików PDF w pliku XML?

Pliki dołączone do faktury elektronicznej są obsługiwane jako osadzone dane binarne w elemencie XML. Serwer SharePoint nie jest potrzebny do osadzenia plików PDF, ale załącznik musi być przechowywany w zarządaniu dokumentami Finance Supply Chain Management i Project Operations.

## <a name="is-electronic-invoicing-service-available-according-to-the-regulations-of-my-countryregion"></a>Czy usługa fakturowania elektronicznego jest dostępna zgodnie z przepisami obowiązującymi w moim kraju/regionie?

Usługa fakturowania elektronicznego jest platformą mikrousługi, która będzie dostępna globalnie.

Firma Microsoft planuje publikować formaty faktur elektronicznych i integracje dla krajów funkcjonalnie zlokalizowanych przez firmę Microsoft. Aby uzyskać więcej informacji, zobacz temat [Dostępność funkcji fakturowania elektronicznego](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Jeśli format fakturowania elektronicznego dla Twojego kraju/regionu nie jest wymieniony, to platforma ma obsługiwać ten scenariusz w przyszłości. Nadal można korzystać z funkcji konfiguracji dostępnej w funkcji fakturowania elektronicznego, a także konfigurować format fakturowania elektronicznego samodzielnie lub samodzielnie konfigurować go z partnerem/użytkownikiem ISV.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Czy dynamics 365 for Regulatory Services jest nowym modułem, jak Zasoby ludzkie czy Project Operations połączonym z modułem Finance lub Supply Chain Management? Czy są za to dodatkowe koszty?

Dynamics 365 for Regulatory Services (RCS) to usługa w chmurze do konfigurowania zasobów globalizacji. Klucz rcs jest bezpłatny dla wszystkich posiadaczy licencji Finance, Supply Chain Management i Project Operations.

Aby zarejestrować się z RCS, przejdź do <https://marketing.configure.global.dynamics.com/>.

Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing-service-or-just-turn-it-on-in-feature-management"></a>Czy muszę się zarejestrować, aby uzyskać usługę fakturowania elektronicznego, czy tylko muszę ją włączyć w zarządzaniu funkcjami?

Jeśli masz licencję Finance, Supply Chain Management, i Project Operations, zobacz temat [Rozpoczynanie pracy z administrowaniem usługami do fakturowania elektronicznego](e-invoicing-get-started-service-administration.md), aby zarejestrować się w celu fakturowania elektronicznego.

## <a name="does-electronic-invoicing-service-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>Czy usługa fakturowania elektronicznego działa z maszynami wirtualnymi warstwy 1? Jakie jest minimalne wymagane środowisko?

Integracja z usługą fakturowania elektronicznego wymaga, aby przynajmniej maszyna wirtualna warstwy 2 obsługiwała Finance lub Supply Chain Management. Aby uzyskać więcej informacji o planowaniu w środowiskach, należy zapoznać się z tematem [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-service-have-a-test-mode-for-testing-invoice-submission"></a>Czy usługa fakturowania elektronicznego działa w trybie testowym testowania przesyłania faktur?

Jest to możliwe dzięki konfiguracji. Aby przetestować przesyłanie faktury, można nawiązać połączenie z Finance lub Supply Chain Management, za pomocą środowiska testu akceptacji użytkownika (UAT) i przesłać faktury testowe. Fakturowanie elektroniczne umożliwia konfigurowanie testowych certyfikatów elektronicznych, a w przypadku faktur elektronicznych wymagających zatwierdzania elektronicznego — konfigurowanie adresu URL testowych usług sieci web opublikowanych przez urzędy skarbowe.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Czy istnieje dokumentacja funkcji fakturowania elektronicznego, które są dostępne w danym kraju?

Tak. Aby uzyskać informacje o dostępności funkcji fakturowania elektronicznego i obsługiwanych przez nie formatach, zobacz temat [Dostępność funkcji fakturowania elektronicznego](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

## <a name="does-the-electronic-invoicing-service-allow-a-legal-entity-in-finance-or-supply-chain-management-that-is-configured-for-a-specific-country-to-consume-electronic-invoicing-features-from-different-countryregions"></a>Czy usługa fakturowania elektronicznego umożliwia osobie prawnej w rozwiązaniu Finance lub Supply Chain Management, który jest skonfigurowany dla określonego kraju, korzystanie z funkcji fakturowania elektronicznego z różnych krajów/regionów?

Tak. Funkcje fakturowania elektronicznego mogą być używane do przetwarzania przesłanych dokumentów biznesowych niezależnie od kraju osoby prawnej, o ile są spełnione następujące wymogi:

   - Generowany dokument biznesowy korzysta z odpowiedniego mapowania modelu dokumentu.
   - Istnieje dopasowanie między dokumentem biznesowym a regułami możliwości zastosowania skonfigurowanymi w funkcji fakturowania elektronicznego.

## <a name="does-the-electronic-invoicing-service-use-the-same-configuration-and-design-experience-provided-by-the-electronic-reporting-module-in-finance-and-supply-chain-management"></a>Czy usługa fakturowania elektronicznego korzysta z tej samej konfiguracji i funkcji projektowania, co moduł raportowania elektronicznego w rozwiązaniach Finance i Supply Chain Management? 

Tak. Te same narzędzia do projektowania, które są używane w module Raportowanie elektroniczne (ER) w rozwiązaniach Finance i Supply Chain Management, są używane do tworzenia i konfigurowania mapowania modelu danych oraz konfiguracji formatów plików. Te narzędzia do projektowania są również używane w rozwiązaniu Regulatory Configuration Services (RCS) do tworzenia i konfigurowania mapowania modelu danych oraz konfiguracji formatów plików, które są używane w konfiguracji funkcji fakturowania elektronicznego.

## <a name="can-the-applicability-rules-be-extended-and-configured-so-that-they-arent-tied-to-any-specific-parameter-such-as-a-legal-entity"></a>Czy reguły możliwości zastosowania mogą być rozszerzane i konfigurowane, aby nie były powiązane z żadnym konkretnym parametrem, takim jak osoba prawna?

Tak. Reguły możliwości zastosowania można w pełni konfigurować. Można dodawać lub usuwać klauzule, tworzyć operacje logiki oraz grupować i rozgrupowywać klauzule. Aby uzyskać więcej informacji, zobacz [Reguły możliwości zastosowania](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#applicability-rules).

## <a name="does-the-electronic-invoicing-service-support-adding-other-er-format-configurations-to-generate-other-types-of-documents-does-it-support-sending-the-documents-electronically-to-customers-such-as-a-delivery-note"></a>Czy usługa fakturowania elektronicznego obsługuje dodawanie innych konfiguracji formatu elektronicznego do generowania innych typów dokumentów? Czy obsługuje wysyłanie dokumentów elektronicznie do odbiorców, takich jak dokument dostawy?

Żądane pliki wyjściowe można tworzyć przy użyciu innych konfiguracji formatów ER. Jednak konfiguracja formatu ER musi być uzyskana na podstawie tego samego mapowania modelu faktury ER, które jest skonfigurowane w rozwiązaniu Finance lub Supply Chain Management, aby generować dokumenty biznesowe. Wysyłanie pliku wyjściowego bezpośrednio do odbiorcy jako transakcji EDI nie jest obsługiwane w fabrycznej konfiguracji fakturowania elektronicznego.

## <a name="does-the-electronic-invoicing-service-support-exchanging-electronic-invoices-with-customers-does-it-support-configuring-different-invoice-formats-for-the-same-invoice"></a>Czy usługa fakturowania elektronicznego obsługuje wymianę faktur elektronicznych z odbiorcami? Czy obsługuje konfigurowanie różnych formatów faktur dla tej samej faktury?

Możliwość otrzymywania i importowania elektronicznych faktur od dostawców jest aktualnie planowana, ale automatyczne wysyłanie faktur elektronicznych do odbiorców nie jest obecnie obsługiwane.

## <a name="does-the-electronic-invoicing-service-extend-to-support-exchanging-edi-messages-with-other-companies"></a>Czy usługa fakturowania elektronicznego rozszerza możliwości wymiany komunikatów EDI z innymi firmami?

Usługi fakturowania elektronicznego skupia się na wymianie typów wiadomości faktury elektronicznej, które są oparte na wymaganiach dotyczących zgodności z przepisami. Odbieranie i importowanie elektronicznych faktur od dostawcy jest obecnie możliwe, jednak wysyłanie plików faktur elektronicznych do odbiorców nie jest obecnie obsługiwane, z wyjątkiem scenariuszy, w których wysyłanie elektronicznej faktury do odbiorcy jest wymagane przepisami.

## <a name="does-the-electronic-invoicing-service-support-importing-or-merging-customizations-made-in-the-er-format-configurations-from-the-legacy-electronic-invoicing-feature"></a>Czy usługa fakturowania elektronicznego obsługuje importowanie lub scalanie dostosowań wykonanych w konfiguracjach formatów elektronicznej wersji ze starszej funkcji fakturowania elektronicznego?

Konfiguracji formatu elektronicznego można używać wielokrotnie w usłudze fakturowania elektronicznego. Jednak konfiguracja formatu ER musi być uzyskana na podstawie tego samego mapowania modelu faktury ER, do którego przeznaczona była funkcja fakturowania elektronicznego i które jest skonfigurowane w rozwiązaniu Finance lub Supply Chain Management, aby generować dokumenty biznesowe.

## <a name="does-the-electronic-invoicing-service-support-issuing-electronic-invoices-from-custom-made-tables-if-so-how-do-you-create-the-er-data-model-configurations-for-these-new-tables-and-entities"></a>Czy usługa fakturowania elektronicznego obsługuje wystawianie faktur elektronicznych z niestandardowych tabel? Jeśli tak, jak należy tworzyć konfiguracje modeli danych ER dla tych nowych tabel i jednostek?

Tak. Wymaga jednak dostosowywania mapowania modelu faktury i dodania niezbędnych odwołań do tabel niestandardowych lub w zależności od złożoności utworzenia nowego mapowania modelu faktury.

## <a name="does-the-electronic-invoicing-service-support-different-web-service-endpoints"></a>Czy usługa fakturowania elektronicznego obsługuje różne punkty końcowe usługi sieci web?

Fakturowanie elektroniczne obsługuje różne punkty końcowe usługi sieci web. Można używać konfigurowalnej integracji z usługami sieci Web REST lub szeregu sparametryzowanych integracji usług sieci Web specyficznych dla kraju. Przy użyciu różnych wersji konfiguracji można skonfigurować różne punkty końcowe tych samych usług sieci Web i interfejsów API. Aby uzyskać więcej informacji, zajrzyj do sekcji [Lista parametrów według akcji](e-invoicing-setup.md#list-of-parameters-by-action).

## <a name="is-electronic-invoicing-integrated-with-the-various-invoice-operators-apis-from-the-nordic-countries-or-should-that-be-handled-on-a-case-by-case-basis"></a>Czy fakturowanie elektroniczne jest zintegrowane z interfejsami API różnych operatorów faktur z krajów skandynawskich, czy też powinny one być obsługiwane indywidualnie?

Firma Microsoft stale rozszerza zakres funkcjonalności, aby zapewnić integracje w konfiguracji fabrycznej przy użyciu funkcji fakturowania elektronicznego. Aby uzyskać więcej informacji o obsługiwanych formatach i integracjach, zobacz [Dostępność funkcji fakturowania elektronicznego](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Jeśli nie udało Ci się znaleźć odpowiedzi, należy wysłać pytanie pocztą e-mail do Zespołu projektowania produktów pod adresem <D365EInvoicePreview@microsoft.com>. Skontaktujemy się z Tobą lub usprawnimy pokrycie tego często zadawanych pytań.
