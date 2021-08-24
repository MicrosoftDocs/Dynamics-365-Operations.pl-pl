---
title: Regulatory Configuration Service
description: W tym temacie przedstawiono omówienie możliwości Regulatory Configuration Service (RCS) i wyjaśniono, jak uzyskać dostęp do usługi.
author: JaneA07
ms.date: 06/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 4ee68b691bba7f3314b5278b0bcc26504c1583335914a1e7c645abd5303f02c6
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012020"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

Regulatory Configuration Service (RCS) to autonomiczna usługa zarządzania projektantem i cyklem życia dla funkcji globalizacji bez kodu/z małą ilością kodu. RCS pozwala interesariuszom zajmującym się globalizacją rozszerzać i dostosowywać kluczowe obszary globalizacji, takie jak podatki, e-fakturowanie, sprawozdawczość regulacyjna, bankowość i dokumenty biznesowe bez konieczności angażowania programistów. Takie podejście do globalizacji bez kodu / z małą ilością kodu sprawia, że globalizacja jest łatwiejsza, szybsza i tańsza w tworzeniu lub rozszerzaniu.

RCS zapewnia następujące możliwości:

- Obsługa wszystkich funkcji udostępnianych przez raportowanie elektroniczne (ER).
- Warunek wstępny do skonfigurowania nowych mikrousług globalizacji.
- Obsługa faktur elektronicznych. Aby uzyskać więcej informacji, zajrzyj do [Faktury elektroniczne](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).
- Obsługuje obliczanie podatku. Aby uzyskać więcej informacji, zobacz [Usługa podatkowa](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).
- Obsługa nowej funkcji globalizacji, która upraszcza zarządzanie cyklem życia funkcji złożonych z wielu komponentów i zapewnia dodatkowe możliwości konfigurowania działań i ustawiania parametrów funkcji. Aby uzyskać więcej informacji, zobacz [Regulatory Configuration Service — uproszczone zarządzanie funkcjami globalizacji dla usług globalizacji](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).
- Obsługa scentralizowanej publikacji, przechowywania i udostępniania niestandardowych konfiguracji w globalnym repozytorium w celu uproszczenia zarządzania konfiguracją bez konieczności korzystania z usług Microsoft Dynamics Lifecycle Services (LCS).

## <a name="access-rcs"></a>Dostęp do RCS

Możesz zarejestrować się lub zalogować się do RCS ze [strony Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

![Rejestracja i logowanie w RCS.](media/202103_RCS%20Marketing%20page_updated_1.jpg)

Na stronie **Regulatory Configuration Service** przejrzyj i zaakceptuj dodatkowe warunki korzystania z usługi, a następnie wybierz jeden z następujących przycisków:

- **Zarejestruj się**, jeśli korzystasz z usługi po raz pierwszy i korzystasz z firmowego adresu e-mail, aby zapewnić swojej organizacji środowisko usługowe
- **Zaloguj się**, jeśli wcześniej zarejestrowałeś się w usłudze i chcesz uzyskać dostęp do środowiska organizacji

> [!NOTE] 
> Po zarejestrowaniu się zaleca się dodanie dodatkowego użytkownika SysAdmin do środowiska RCS. Ten użytkownik zostanie aprowizowana jako współadministrator środowiska. Pomoże to zapewnić stabilność dostępu do środowiska RCS, ponieważ rolą SysAdmin jest zarządzanie użytkownikami dla tego środowiska. Użytkownicy można dodawać za pomocą **Obszaru roboczego RCS > Administracji systemu**.

## <a name="regional-availability"></a>Dostępność regionalna

RCS jest ogólnie dostępny w następujących regionach:

- Stany Zjednoczone
- Indie
- Francja
- Europa

Aby uzyskać pełną listę regionów, zobacz temat [Dynamics 365 oraz Power Platform: Dostępność, lokalizacja danych, język i lokalizacja](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="rcs-default-company"></a>Domyślna firma RCS

Funkcjonalność czasu projektowania, która jest używana w RCS jest wspólna dla wszystkich firm. Brak funkcji specyficznych dla firmy. Dlatego rekomendujemy, abyś używał jednej firmy, **DAT**, w swoim środowisku RCS.

Jednak w niektórych scenariuszach możesz chcieć, aby formaty ER wykorzystywały parametry, które są związane z konkretnym podmiotem prawnym. Tylko w tych scenariuszach należy używać domyślnego przełącznika firm. Na przykład: [Konfiguracja formatów raportowania elektronicznego do używania parametrów określonych dla firmy](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).

## <a name="related-rcs-documentation"></a>Powiązana dokumentacja RCS

Aby uzyskać więcej informacji na temat powiązanych komponentów, zapoznaj się z następującymi tematami:

- **RCS:**

    - [Tworzenie konfiguracji raportowania elektronicznego w RCS i przekazywanie ich do repozytorium globalnego](rcs-global-repo-upload.md)

- **Globalne repozytorium:**

    - [Utwórz konfigurację ER i prześlij do repozytorium globalnego](rcs-global-repo-upload.md)
    - [Udostępnianie konfiguracji w globalnym repozytorium](rcs-global-repo-share-configuration.md)
    - [Ulepszone filtrowanie w globalnym repozytorium](enhanced-filtering-global-repo.md)
    - [Pobieranie konfiguracji modułu Raportowanie elektroniczne z globalnego repozytorium](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Wycofywanie konfiguracji w repozytorium globalnym](discontinuing-configurations-rcs-global-repo.md)
    - [Regulatory Configuration Service (RCS) — deprekacja pamięci w Lifecycle Services (LCS)](rcs-lcs-repo-dep-faq.md)

- **Funkcje globalizacji:**

    - [Regulatory Configuration Service (RCS) — funkcje globalizacji](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a>Rozwiązywanie problemów dotyczących podatku od towarów i usług (RCS) — rejestracja

Podczas rejestracji w RCS ze strony usługi może wystąpić problem związany z Azure Active Directory (Azure AD). Komunikat o błędzie, który otrzymujesz wskazuje, że rejestracja do RCS jest obecnie wyłączona i musi zostać włączona, byś mógł dokończyć proces rejestracji.

![Komunikat o błędzie rejestracji RCS.](media/01_RCSSignUpError.jpg)

Problem występuje, ponieważ użytkownik ma zablokowaną opcję rejestracji na subskrypcje ad hoc, a właściwość `AllowAdHocSubscriptions` musi być włączona w dzierżawie. 

- Jeśli dział IT zarządza lokatorami Azure w organizacji, należy skontaktować się z tym działem w celu zgłoszenia problemu.
- Jeśli odpowiadasz za zarządzanie dzierżawami systemu Azure, możesz rozwiązać problem, wykonać kroki opisane w: [Czym jest samoobsługowa rejestracja w Azure Active Directory](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings).
