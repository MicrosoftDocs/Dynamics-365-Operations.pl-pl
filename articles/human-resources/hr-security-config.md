---
title: Koncepcje konfiguracji zabezpieczeń dotyczących integracji wirtualnych tabel
description: W tym artykule wyjaśniono architektura budowania integracji między firmą Microsoft Dynamics 365 Human Resources i innymi systemami.
author: twheeloc
ms.date: 11/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 219ceb0adae0cee5f74a39140ab74af9fdac1eb6
ms.sourcegitcommit: ea79bf014bbf495ac8e28db29502c8bd85a75f32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2022
ms.locfileid: "9759658"
---
# <a name="security-configuration-concepts-for-virtual-table-based-integrations"></a>Koncepcje konfiguracji zabezpieczeń dotyczących integracji wirtualnych tabel

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano architekturę umożliwiającą korzystanie z [Microsoft Dataverse wirtualnych tabel (obiektów)](/dev-itpro/power-platform/virtual-entities-overview) do tworzenia integracji między Dynamics 365 Human Resources a systemem innej firmy. Artykuł koncentruje się na konfiguracji zabezpieczeń oraz aspektach uwierzytelniania i autoryzacji, które są wymagane między granicami systemu, aby zbudować funkcjonalny, bezpieczny system.

## <a name="prerequisite-reference-articles"></a>Artykuły z odwołaniami do wymagań wstępnych

Poniższe artykuły zawierają więcej informacji na temat pojęć w tym artykule:

- [Jednostki wirtualne — omówienie](/dev-itpro/power-platform/virtual-entities-overview)
- [Rozpoczynanie pracy z tabelami wirtualnymi (jednostkami)](/developer/data-platform/virtual-entities/get-started-ve)
- [Użyj uwierzytelniania serwer-serwer z wieloma dzierżawcami (Microsoft Dataverse)](/developer/data-platform/use-multi-tenant-server-server-authentication)
- [Użyj uwierzytelniania OAuth z Microsoft Dataverse (Dataverse)](/developer/data-platform/authenticate-oauth)
- [Poświadczenia klienta OAuth 2.0 przepływają na platformie tożsamości firmy Microsoft](/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow)
- [Uwierzytelnianie i autoryzacja](/dev-itpro/power-platform/authentication-and-authorization)

## <a name="architecture"></a>Architektura 

Na poniższym diagramie architektury przedstawiono główne koncepcje związane z integracją korzystającą z wirtualnych tabel (jednostek).

![Integracja oparta na tabeli wirtualnej.](./media/Hosts.jpg)

Oto wyjaśnienie niektórych elementów poprzedniego diagramu:

- **Microsoft** — Microsoft hostuje i obsługuje różne produkty Dynamics 365 w imieniu klientów.

    - **Azure Active Directory (Azure AD) Dzierżawa C** — dzierżawa Azure AD należąca do Microsoft. Jest to dzierżawa, w których są rejestrowane aplikacje Dynamics 365.

- **Partner integrowania**

    - **System integrowania** — system integrowany z systemem Dynamics 365. Może to być system płac lub dowolny system, który opiera się na danych przechowywanych w usłudze Dynamics 365.
    - **Adapter** — oprogramowanie lub usługa odpowiedzialna za interakcję z systemem Dynamics 365 i systemem integrowania.

        > [!NOTE]
        > Jeśli adapter ma być używany przez wielu odbiorców systemu Dynamics 365, należy się rejestrować jako wielowątkową aplikację w systemie Azure AD.

    - **Dzierżawca A Azure AD** — dzierżawa Azure AD należąca do partnera integratora. Jest to dzierżawca, w którym zarejestrowany jest identyfikator aplikacji adaptera.

- **Wzajemny odbiorca** — odbiorca implementuje Dynamics 365 Human Resources i integruje rozwiązanie partnera.

    - **Dynamics 365 — Finance lub Human Resources** — Specyficzne dla klienta wystąpienie Dynamics 365 Finance lub Human Resources, które zawiera dane klienta wymagane przez system integrujący.
    - **Dataverse** — środowisko specyficzne dla odbiorcy Dataverse, które jest połączone z Finance lub Human Resources. Dataverse oferuje interfejs API sieci Web do interakcji z danymi usługi Dynamics 365.
    - **Dzierżawca B Azure AD** — dzierżawca Azure AD odbiorcy. Działa jako dostawca tożsamości (serwer autoryzacji) i wydaje tokeny, które autoryzują wywołania wystąpienia Dataverse odbiorcy.

## <a name="basic-request-flow"></a>Podstawowy przepływ żądań

W tej sekcji opisano podstawowy przepływ typowych żądań związanych z integracją. Odwołuje się on do diagramu architektury wcześniej w tym artykule.

Typowe żądanie wymaga, aby adapter kwerendy Dynamics 365 dla danych, a następnie zapisywał i synchronizować te dane z systemem integrowania.

1. Adapter wywołuje interfejs API sieci Web Dataverse w celu wysłania zapytania o odpowiednie dane.

    > [!NOTE]
    > Uwierzytelnianie jest warunkiem wstępnym, a nabycie tokenu jest główną częścią procesu. Uwierzytelnianie zostanie opisane w sekcji [Uwierzytelnianie i autoryzacja w granicach systemu](#authentication-and-authorization-at-system-boundaries).

    To wywołanie jest adresowane do interfejsu API sieci Web Dataverse w celu wykonywania kwerendy o dane aplikacji udostępniane za pośrednictwem tabeli wirtualnej. (Patrz „2. Synchronizacja początkowa” i „3. Delta Sync” na schemacie.)

2. Dataverse obsługuje żądanie, wysyłając zapytanie do tabeli wirtualnej za pośrednictwem wtyczki jednostki wirtualnej („Proxy wirtualnej tabeli” na diagramie). Żądanie Dataverse jest przekazywane do usługi jednostki wirtualnej Zasoby ludzkie lub finanse w celu wykonywania kwerendy dotyczącej danych fizycznie przechowywanych w bazie danych Zasoby ludzkie lub finanse.
3. Usługa jednostki wirtualnej Finance lub Human Resources tłumaczy żądanie skierowane do jednostki wirtualnej na zapytanie skierowane do jednostki Finance lub Human Resources, która obsługuje jednostkę wirtualną Dataverse. Dane są pobierane z bazy danych, tłumaczone z powrotem na reprezentację jednostki Dataverse i zwracane do wywołującego.
4. Adapter kończy wszelkie wymagane odwzorowania i translację danych oraz wywołuje system integrujący w celu utrwalenia danych w bazie danych systemu integrującego. (Patrz „4. Zapisz dane” na diagramie).

## <a name="authentication-and-authorization-at-system-boundaries"></a>Uwierzytelnianie i autoryzacja na granicach systemu

*Uwierzytelnianie* sprawdza, czy tożsamość użytkownika lub aplikacji została potwierdzona, i potwierdza, że użytkownik lub aplikacja jest tym, na którym się znajduje. *Autoryzacja* udziela użytkownikowi lub aplikacji prawa dostępu do określonych uprawnień na poziomie aplikacji. Aby uzyskać więcej informacji, zobacz [uwierzytelnianie a autoryzacja](/azure/active-directory/develop/authentication-vs-authorization).

Większość wywołań między systemowych na diagramie architektury wcześniejszej w tym artykule dotyczy tego adaptera. Adapter musi dokonać uwierzytelniania samego siebie, aby wykonać następujące wywołania:

- Wezwanie do Dataverse
- Wywołanie systemu integrowania

Sprawdź granice systemu na diagramie. Każde żądanie sieci web między systemami musi zostać uwierzytelnione, a sprawdzanie autoryzacji na poziomie aplikacji musi zostać przekazane przed zwróceniem danych do wywołania. W przypadku żądania uwierzytelniania i autoryzacji tabeli wirtualnej systemu Dynamics 365, która jest finansowana przez finanse lub zasoby ludzkie, uwierzytelnianie i autoryzacja są wymuszane przy następujących granicach systemu:

- Wywołanie między adapterem a punktem końcowym interfejsu API sieci Web Dataverse (OData)
- Wywołanie między wtyczką podmiotu wirtualnego Dataverse a usługą podmiotu wirtualnego Finance lub Human Resources

W obu przypadkach testy uwierzytelniania są wykonywane w pierwszej kolejności. Następnie wykonywane są testy autoryzacji na poziomie aplikacji, aby upewnić się, że uwierzytelniony użytkownik lub aplikacja ma prawidłowe uprawnienia na poziomie aplikacji do pobierania żądanych danych.

Uwierzytelnianie w celu wywołania Dataverse jest obsługiwane przez token okaziciela, który musi być dołączony jako nagłówek HTTP w żądaniu internetowym do Dataverse. Adapter musi pobrać token z wystąpienia dzierżawy B Azure AD. (Patrz „1. Pobierz token” na diagramie). Azure AD działa jako dostawca tożsamości w przepływie uwierzytelniania.

Adapter uwierzytelnia się, podając jego tożsamość aplikacji (nietajemną, zarejestrowaną w dzierżawie A Azure AD) oraz tajny klucz aplikacji lub certyfikat, który ma tylko aplikacja adaptera.

Po uwierzytelnieniu użytkownika lub aplikacji w celu nawiązywania połączeń z Dataverse, dla każdego żądania przeprowadzane są kontrole autoryzacji na poziomie Dataverse. Sprawdzenie zapewnia, że wywołująca (tożsamość aplikacji adaptera, oznaczona jako „\<guid A\>” na diagramie) ma odpowiednie uprawnienia aplikacji. Autoryzacja na poziomie aplikacji jest zarządzana w Dataverse za pośrednictwem użytkownika aplikacji, który reprezentuje identyfikator aplikacji adaptera. Uprawnienia na poziomie aplikacji są zarządzane przez przyznanie dostępu do określonych zdefiniowanych ról aplikacji Dataverse. Te role zapewniają szczegółowe uprawnienia aplikacji.

Aby uzyskać bardziej szczegółowe wskazówki, zob [Użyj uwierzytelniania między serwerami dla wielu dzierżawców](/power-apps/developer/data-platform/use-multi-tenant-server-server-authentication).

Jeśli sprawdzanie uprawnień aplikacji na poziomie Dataverse zostanie przekazane, dodatek plug-in Jednostka wirtualna wywołuje wywołanie punktu końcowego usługi jednostki wirtualnej w środowisku zasoby ludzkie i finanse. To wywołanie jest uwierzytelnianie od serwera do serwera (S2S). Używa tożsamości i tajnych danych skonfigurowanych w rekordzie konfiguracji wirtualnego źródła danych firmy Finance i Operations.

![Rekord konfiguracji wirtualnego źródła danych rozwiązania Finance i Operations w środowisku piaskownicy.](./media/sandbox.jpg)

Aby uzyskać więcej informacji, zobacz [Konfiguracja wirtualnych encji Dataverse](/dev-itpro/power-platform/admin-reference).

Wywołanie z wtyczki jednostki wirtualnej Dataverse do działu Finance lub Human Resources obejmuje tożsamość adaptera oryginalnego wywołania do Dataverse z adaptera (tożsamość oznaczona jako „\<guid A\>” na diagramie architektury). Jeśli źródło danych jednostki wirtualnej jest poprawnie skonfigurowane i sprawdzanie uwierzytelniania S2S jest przekazane, usługa jednostki wirtualnej w finansach lub zasobach ludzkich uruchamia kwerendę w kontekście oryginalnego elementu wywołującego (adapter \<guid A\>). Sprawdzenie uprawnień aplikacji (autoryzacja) na poziomie finansów lub zasobów ludzkich zostanie przeprowadzone w celu upewnienia się, że adapter ma uprawnienia wymagane do uzyskania dostępu do jednostek danych żądanych za pośrednictwem zapytania.

Zabezpieczenia w finansach i zasobach ludzkich są zarządzane w następujący sposób:

1. Mapowanie tożsamości adaptera (\<guid A\>) na określonego użytkownika w poszczególnych finansach lub zasobach ludzkich. To mapowanie jest wykonywane na stronie aplikacji **usługi Azure Active Directory**. Aby uzyskać więcej informacji, zobacz [Rejestrowanie aplikacji zewnętrznej](/dev-itpro/data-entities/services-home-page.md#register-your-external-application).
2. Przez przyznanie użytkownikowi „finanse” lub „zasoby ludzkie” odpowiednich ról, obowiązków i uprawnień na poziomie aplikacji. Więcej informacji zawiera temat [Zabezpieczenia oparte na rolach](/dev-itpro/sysadmin/role-based-security).

Jeśli aplikacja adaptera (\<guid A\>) ma przyznane uprawnienia wymagane do uzyskania dostępu do żądanych danych, mają miejsce następujące zdarzenia:

1. Zapytanie jest uruchamiane.
2. Dane są tłumaczone z powrotem na stronę jednostki Dataverse.
3. Dane są zwracane do adaptera.

> [!IMPORTANT]
> Podczas tworzenia adaptera można uruchomić za pomocą użytkownika z rolą Administrator w ustawieniach finansowych lub ludzkich. Jednak w środowisku produkcyjnym adapter nigdy nie powinien być uruchamiany z uprawnieniami administratora.

## <a name="key-takeaways"></a>Podjąć klucza

Oto kilka istotnych skutków architektury tabeli wirtualnej lub jednostki:

- Konfiguracja zabezpieczeń tabel wirtualnych, które są kopiiowane przez zasoby ludzkie, jest zarządzana w zasobach ludzkich.
- Odbiorca („Wzajemny odbiorca” na diagramie architektury wcześniejszej niż ten artykuł) ma pełną kontrolę nad tym, jakie uprawnienia są przyznawane tożsamości adaptera integrowania (oznaczonego jako „\<guid A\>” na diagramie).
- Odbiorca jest odpowiedzialny za poprawną konfigurację zabezpieczeń w swoim środowisku zasobów ludzkich. Partner integrujący, który tworzy adapter, musi podać wskazówki dotyczące uprawnień wymaganych przez adapter.
