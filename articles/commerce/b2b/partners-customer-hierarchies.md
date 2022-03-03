---
title: Zarządzanie partnerami biznesowymi B2B przy użyciu hierarchii klientów
description: W tym temacie opisano, jak używać hierarchii klientów do zarządzania partnerami biznesowymi w witrynach e-commerce Microsoft Dynamics 365 Commerce typu business-to-business (B2B).
author: josaw1
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d6e594cbb824a8b823912118e99b819585adc45e
ms.sourcegitcommit: 8bcb9c13eccb14e61c39ca6578d135b64090fad2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2022
ms.locfileid: "8313835"
---
# <a name="manage-b2b-business-partners-using-customer-hierarchies"></a>Zarządzanie partnerami biznesowymi B2B przy użyciu hierarchii klientów

[!include [banner](../../includes/banner.md)]

W tym temacie opisano, jak używać hierarchii klientów do zarządzania partnerami biznesowymi w witrynach e-commerce Microsoft Dynamics 365 Commerce typu business-to-business (B2B).

W centrali handlowej jednostka *hierarchia klientów* jest używana do reprezentowania organizacji partnerów biznesowych, które będą korzystać z Twojej witryny handlu elektronicznego B2B. Zanim zaczniesz używać hierarchii klientów do zarządzania partnerami biznesowymi, musisz włączyć funkcje handlu elektronicznego B2B w centrali handlowej, a następnie zdefiniować sekwencję numerów dla hierarchii klientów.

## <a name="enable-the-b2b-e-commerce-feature-in-commerce-headquarters"></a>Włącz funkcję e-commerce B2B w centrali Commerce

Aby korzystać z funkcji B2B e-commerce, musisz najpierw włączyć funkcję **Włącz korzystanie z funkcji B2B eCommerce** w centrali handlowej.

1. Kliknij kolejno opcje **Obszary robocze \> Zarządzanie funkcjami**.
1. Na tablecie **Wszystko** użyj pola filtrowania, aby wyszukać **Moduł: Handel detaliczny i handel**.
1. Znajdź funkcję **Włącz korzystanie z funkcji handlu elektronicznego B2B**, wybierz ją, a następnie wybierz **Włącz teraz** w prawym dolnym rogu.

## <a name="define-a-number-sequence-for-the-customer-hierarchy"></a>Zdefiniuj sekwencję numerów dla hierarchii klientów

Sekwencje numerów są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które muszą mieć identyfikatory. Należy zdefiniować sekwencję numerów, która będzie używana do generowania identyfikatora dla hierarchii klientów. Aby uzyskać więcej informacji na temat sekwencji numerów, zobacz temat pomocy [Omówienie sekwencji numerów](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview).

Aby zdefiniować sekwencję numerów dla hierarchii klientów w centrali handlowej, wykonaj następujące kroki.

1. Przejdź do **Retail i Commerce \> Ustawienia centrali \> Numery kolejne \> Numery kolejne**.
1. Utwórz nową sekwencję numerów lub wybierz istniejącą, aby użyć jej ponownie.
1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Wspólne parametry handlu**.
1. Na karcie **Sekwencje numerów** dodaj utworzoną lub wybraną wcześniej sekwencję numerów do odwołania **do identyfikatora hierarchii odbiorcy**.

![Sekwencja numerów dodawana do odwołania do identyfikatora hierarchii klientów.](../media/NumberSequenceCustHierarchy.png)

## <a name="how-the-approval-process-works"></a>Jak działa proces zatwierdzania

Gdy partner biznesowy żąda dołączenia do witryny B2B e-commerce, system zapisuje żądanie jako *prospekt*. Osoba z centrali handlowej, taka jak kierownik ds. operacji detalicznych, może zatwierdzać lub odrzucać prośby partnerów. Aby uzyskać więcej informacji na temat zarządzania prośbami o partnerów biznesowych i zatwierdzeniami potencjalnych klientów, zobacz [Zarządzanie użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B](manage-b2b-users.md).

Po zatwierdzeniu prospektu system tworzy dwa nowe rekordy klientów:

- Jeden rekord odbiorcy typu **Organizacja** reprezentuje organizację, która żąda zostać partnerem biznesowym.
- Jeden rekord odbiorcy typu **Osoba** reprezentuje osobę, która przesłała wniosek.

Ponadto nowy rekord hierarchii odbiorców jest tworzony w **Handel detaliczny \> Klienci \> Hierarchie klientów**. Ten rekord hierarchii klientów ma następujące właściwości:

- **Identyfikator hierarchii odbiorcy** – Unikalny identyfikator hierarchii klientów. Ten identyfikator wykorzystuje sekwencję numerów zdefiniowaną w parametrach współdzielonych Commerce.
- **Nazwa** — nazwa organizacji partnera biznesowego, określona w żądaniu przysyłania. To pole można edytować.
- **Cel** — właściwość jest ustawiona na wstępnie zdefiniowaną wartość **organizacji B2B**.
- **Organizacja** — Identyfikator klienta organizacji partnera biznesowego.

Osoba, która przesłała prośbę o włączenie, jest dodawana na skróconej karcie **Hierarchia** i przypisywana jest jej rola **Administrator**. Gdy administrator dodaje kolejnych użytkowników do organizacji partnera biznesowego w witrynie B2B, dla każdego użytkownika tworzony jest nowy rekord klienta. Rekord klienta jest również dodawany do odpowiedniego rekordu hierarchii klientów dla partnera biznesowego i jest do niego przypisywana rola **Użytkownik**.

### <a name="examples"></a>Przykłady

Osoba o imieniu Sam J. przesyła żądanie przyjścia do pracy w imieniu organizacji firmy Microsoft. Gdy wniosek zostanie zatwierdzony, tworzone są dwa nowe konta odbiorcy: jedno z typu **Osoba** dla Sama J. i jedno z typów **organizacji** dla firmy Microsoft.

Jak pokazano na poniższej ilustracji, zostanie również utworzony nowy rekord hierarchii odbiorcy. Ten rekord ma taką samą nazwę jak organizacja (**Microsoft**), a rola **Administrator** jest przypisana do Sama J. Jako administrator, Sam J. dodaje do tej hierarchii wszystkich innych użytkowników firmy Microsoft witryny B2B i przypisuje do nich **użytkownika**. W tym przykładzie Sush R. został dodany jako użytkownik.

![Przykład rekordu hierarchii klientów.](../media/CustomerHierarchy2.png)

Aby ustalić, czy klient jest powiązany z hierarchią klientów, otwórz rekord klienta. Jak pokazano w przykładzie na poniższej ilustracji, pole **Identyfikator hierarchii klientów** w sekcji **B2B** na skróconej karcie **Sprzedaż detaliczna** FastTab pokazuje, czy klient jest częścią hierarchii klientów, a Opcja **administrator B2B** wskazuje, czy klient jest administratorem tej hierarchii.

![Przykład sekcji B2B na skróconej karcie Sprzedaż detaliczna rekordu klienta, w której klient jest powiązany z hierarchią i określony jako administrator.](../media/CustomerHierarchyMapping2.png)

W większości przypadków wartości właściwości wszystkich rekordów klientów w hierarchii powinny być zgodne. Na przykład, ponieważ wszyscy użytkownicy partnerów biznesowych powinni otrzymywać podobne ceny produktów, ich grupy cenowe i powiązane konfiguracje powinny być zgodne. Jednak system nie wymusza tej spójności. W związku z tym odpowiedni użytkownicy Commerce headquarters są odpowiedzialni za zapewnienie, że wartości właściwości i konfiguracje są zgodne dla wszystkich klientów w danej hierarchii.

Użytkownicy centrali handlowej mogą sprawdzać wartości właściwości dla wszystkich rekordów klientów w hierarchii w widoku obok siebie. Na poniższej ilustracji pokazano, że można użyć opcji **Ogólne** na liście rozwijanej na skróconej karcie **hierarchii**, a następnie wybrać dowolną sekcję rekordu odbiorcy w celu pokazania powiązanych właściwości. Użytkownicy mogą edytować wartości właściwości bezpośrednio w tym widoku. Aby skopiować wszystkie wartości z rekordu odbiorcy administratora do wszystkich użytkowników, wybierz pozycję **Zastąp** na skróconej karcie **hierarchii**.

![Przykład rekordu hierarchii odbiorcy, pokazujący przycisk Zastąp i opcję z listy rozwijanej.](../media/HierarchyDetails2.png)

[!include [footer-include](../../includes/footer-banner.md)]
