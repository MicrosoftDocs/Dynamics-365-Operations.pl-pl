---
title: Fakturowanie elektroniczne — FAQ
description: Ten temat zawiera informacje dotyczące często zadawanych pytań dotyczących fakturowania elektronicznego.
author: gionoder
ms.date: 03/17/2021
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
ms.openlocfilehash: 41cddcdad5043ec314a94dda67f4f2e9de406cac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840179"
---
# <a name="electronic-invoicing-faq"></a>Fakturowanie elektroniczne — FAQ

[!include [banner](../includes/banner.md)]

Ten temat zawiera odpowiedzi dotyczące często zadawanych pytań dotyczących fakturowania elektronicznego. Fakturowanie elektroniczne rozszerza możliwości fakturowania elektronicznego istniejące w Dynamics 365 Finance, Dynamics 365 Supply Chain Management i Dynamics 365 Project Operations. 

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

## <a name="does-electronic-invoicing-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>Czy fakturowanie elektroniczne obsługuje lokalne instalacje Finance, Supply Chain Management i Project Operations? 

Bieżąca platforma nie zezwala na używanie lokalnej wersji i nie ma planów, aby ją obsługiwać w przyszłości.

## <a name="does-electronic-invoicing-interface-with-the-vendor-import-automation-feature"></a>Czy interfejs fakturowania elektronicznego z funkcją automatyzacji importu dostawców?

Nr Istnieją plany dla tego interfejsu, ale nie zaplanowano osi czasu. Jeśli to planowane, daty będą się dzieje w [Planach zwalniania](https://docs.microsoft.com/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>W jaki sposób fakturowanie elektroniczne obsługuje załączniki plików do faktury elektronicznej? Czy serwer SharePoint jest potrzebny do osadzania plików PDF w pliku XML?

Pliki dołączone do faktury elektronicznej są obsługiwane jako osadzone dane binarne w elemencie XML. Serwer SharePoint nie jest potrzebny do osadzenia plików PDF, ale załącznik musi być przechowywany w zarządaniu dokumentami Finance Supply Chain Management i Project Operations.

## <a name="is-electronic-invoicing-available-according-to-the-regulations-of-my-countryregion"></a>Czy fakturowanie elektroniczne jest dostępne zgodnie z przepisami obowiązującymi w moim kraju/regionie?

Fakturowanie elektroniczne jest platformą mikrousługi, która będzie dostępna globalnie.

Firma Microsoft planuje publikować formaty faktur elektronicznych i integracje dla krajów funkcjonalnie zlokalizowanych przez firmę Microsoft. Aby uzyskać więcej informacji, zobacz temat [Dostępność funkcji fakturowania elektronicznego](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Jeśli format fakturowania elektronicznego dla Twojego kraju/regionu nie jest wymieniony, to platforma ma obsługiwać ten scenariusz w przyszłości. Nadal można korzystać z funkcji konfiguracji dostępnej w funkcji fakturowania elektronicznego, a także konfigurować format fakturowania elektronicznego samodzielnie lub samodzielnie konfigurować go z partnerem/użytkownikiem ISV.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Czy dynamics 365 for Regulatory Services jest nowym modułem, jak Zasoby ludzkie czy Project Operations połączonym z modułem Finance lub Supply Chain Management? Czy są za to dodatkowe koszty?

Dynamics 365 for Regulatory Services (RCS) to usługa w chmurze do konfigurowania zasobów globalizacji. Klucz rcs jest bezpłatny dla wszystkich posiadaczy licencji Finance, Supply Chain Management i Project Operations.

Aby zarejestrować się z RCS, przejdź do <https://marketing.configure.global.dynamics.com/>.

Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Services (RCS) – funkcje globalizacji](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing--or-just-turn-it-on-in-feature-management"></a>Czy musisz się zarejestrować, aby można było uzyskać fakturowanie elektroniczne, czy tylko włączyć go w zarządzaniu funkcjami?

Jeśli masz licencję Finance, Supply Chain Management, i Project Operations, zobacz temat [Rozpoczynanie pracy z administrowaniem usługami do fakturowania elektronicznego](e-invoicing-get-started-service-administration.md), aby zarejestrować się w celu fakturowania elektronicznego.

## <a name="does-electronic-invoicing-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>Czy fakturowanie elektroniczne działa z maszynami wirtualnymi warstwy 1? Jakie jest minimalne wymagane środowisko?

Integracja z fakturowaniem elektronicznym wymaga, aby przynajmniej maszyna wirtualna warstwy 2 obsługiwała Finance lub Supply Chain Management. Aby uzyskać więcej informacji o planowaniu w środowiskach, należy zapoznać się z tematem [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-have-a-test-mode-for-testing-invoice-submission"></a>Czy fakturowanie elektroniczne działa w trybie testowym testowania przesyłania faktur?

Jest to możliwe dzięki konfiguracji. Aby przetestować przesyłanie faktury, można nawiązać połączenie z Finance lub Supply Chain Management, za pomocą środowiska testu akceptacji użytkownika (UAT) i przesłać faktury testowe. Fakturowanie elektroniczne umożliwia konfigurowanie testowych certyfikatów elektronicznych, a w przypadku faktur elektronicznych wymagających zatwierdzania elektronicznego — konfigurowanie adresu URL testowych usług sieci web opublikowanych przez urzędy skarbowe.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Czy istnieje dokumentacja funkcji fakturowania elektronicznego, które są dostępne w danym kraju?

Tak. Aby uzyskać informacje o dostępności funkcji fakturowania elektronicznego i obsługiwanych przez nie formatach, zobacz temat [Dostępność funkcji fakturowania elektronicznego](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Jeśli nie udało Ci się znaleźć odpowiedzi, należy wysłać pytanie pocztą e-mail do Zespołu projektowania produktów pod adresem <D365EInvoicePreview@microsoft.com>. Skontaktujemy się z Tobą lub usprawnimy pokrycie tego często zadawanych pytań.
