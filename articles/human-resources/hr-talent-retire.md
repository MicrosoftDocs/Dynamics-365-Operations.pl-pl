---
title: Wycofanie Dynamics 365 Talent – Attract i Onboard
description: Ten temat opisuje wycofanie z użytku aplikacji Dynamics 365 Talent Attract i Onboard.
author: twheeloc
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e17b92621f05ad8483a7c578bfaece58a530df2d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692010"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Wycofanie Dynamics 365 Talent: Attract i Onboard


W grudniu 2019 r. ogłosiliśmy wycofanie aplikacji Dynamics 365 Talent - Attract i Onboard z dniem 1 lutego 2022 r., dając naszym klientom dwa lata na przygotowanie się do zmiany.

Więcej informacji na temat wycofania tych aplikacji z użytku znajdziesz na stronie:
 - [Wycofywanie aplikacji Dynamics 365 Talent ‑ Attract i Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [Budowanie bardziej skutecznej siły roboczej z Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

Będziemy nadal wspierać Dynamics 365 Human Resources, co pomoże naszym klientom uzyskać wgląd w pracowników, niezbędny do budowania opartych na danych doświadczeń pracowniczych w wielu obszarach, takich jak:

- Kompensata
- Korzyści
- Urlopy i nieobecności
- Zgodność
- Payroll
- Opinia dotycząca wyników
- Szkolenie i certyfikacja
- Programy do samoobsługi

## <a name="dynamics-365-talent-apps-retirement-faq"></a>FAQ: Wycofanie aplikacji Dynamics 365 Talent

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>Jakie jest doświadczenie użytkownika dla obu aplikacji Dynamics 365 Talent Attract i Onboard od 1 lutego 2022 roku?

Użytkownicy nie będą mogli korzystać z aplikacji i zostaną przekierowani na stronę przejścia na emeryturę.

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>Czy klienci mogą kontynuować eksport danych dla obu aplikacji Dynamics 365 Talent - Attract i Onboard po 1 lutego 2022 roku?
  
Nie, wycofanie zostało ogłoszone w grudniu 2019 roku, a wymagane zdolności eksportowe zostały zapewnione do 1 lutego 2022 roku. 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>Czy dane klienta związane z obiema aplikacjami Dynamics 365 Talent - Attract i Onboard w Dataverse zostaną usunięte po 1 lutego 2022 roku?

Nie, jednostki Dataverse pozostaną w środowisku Microsoft Dataverse klienta nawet po przejściu na emeryturę, chyba że rozwiązanie Human Capital Management Talent zostanie usunięte lub odinstalowane.

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>Znam nazwę środowiska Talent. Jak mogę zobaczyć dane Attract i Onboard w Dataverse?

1.  Zaloguj się w rozwiązaniu Power Apps: https://make.powerapps.com
2.  Wybierz środowisko, w którym chcesz zobaczyć dane dotyczące Attract i Onboard.
3.  Przejdź do **Dataverse > Tabele**. 
4.  Wpisz „msdyn_” w **Wyszukiwaniu**. Jeśli widzisz listę tabel zaczynających się od "msdyn_" + nazwy tabel (przykład: msdyn_candidate) to znalazłeś środowisko z danymi Attract i Onboard.

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>Nie znam nazwy środowiska Talent. Jak mogę znaleźć środowisko, które posiada dane dla aplikacji Dynamics 365 Talent: Attract i Dynamics 365 Talent: Onboard?

1)  Zaloguj się do centrum administracyjnego Power Platform: https://admin.powerplatform.microsoft.com/
2)  Wybierz opcję **Środowiska**.
3)  Wybierz konkretne środowisko do ewaluacji.
4)  Wybierz pozycję **Zasoby > Aplikacje Dynamics 365**.
5)  Jeśli jest zainstalowane rozwiązanie **HCM Talent**, w tym środowisku powinny być przechowywane dane Attract i Onboard. 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> Rozwiązanie **HCM Talent** jest również używane w rozwiązaniu Dynamics 365 Human Resources.
