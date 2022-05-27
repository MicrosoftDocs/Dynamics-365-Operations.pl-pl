---
title: Konfiguracja korzystania z modułu Finance Insights
description: W tym temacie objaśniono kroki konfiguracyjne, które umożliwią systemowi korzystanie z funkcji dostępnych w module Finance Insights.
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 6ec7e6a7e616e239128281ba669c8bbbfc5e3c7a
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710638"
---
# <a name="configuration-for-finance-insights"></a>Konfiguracja korzystania z modułu Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Finance Insights łączy funkcje firmy Microsoft Dynamics 365 Finance z Dataverse, Azure i AI Builder w celu zapewnienia wydajnego narzędzia prognozowania dla organizacji. W tym temacie objaśniono kroki konfiguracyjne, które umożliwią systemowi korzystanie z funkcji dostępnych w module Finance Insights. Aby pomyślnie wykonać procedury opisane w tym temacie, musisz mieć dostęp administratora systemu i konfiguratora systemu w [Centrum administracyjne Power Portal](https://admin.powerplatform.microsoft.com/), dostęp administratora systemu w Dynamics 365 Finance, oraz dostęp do tworzenia środowisk w Microsoft Dynamics Lifecycle Services (LCS).

> [!NOTE]
> Poniższe procedury konfigurowania rozwiązania Finance Insights są prawidłowe w przypadku wersji rozwiązania Microsoft Dynamics 365 Finance do 10.0.21 i nowszych.

## <a name="deploy-dynamics-365-finance"></a>Wdrażanie Dynamics 365 Finance

Wykonaj poniższe kroki, aby wdrożyć środowiska.

1. W LCS utwórz lub zaktualizuj środowisko Dynamics 365 Finance. Środowisko wymaga wersji aplikacji 10.0.21 lub nowszej.

    > [!NOTE]
    > Środowisko musi być środowiskiem o wysokiej dostępności (HA). (Środowisko tego typu jest również nazywane środowiskiem warstwy 2) Aby uzyskać więcej informacji, zobacz [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

2. Jeśli konfigurujesz Finance Insights w środowisku piaskownicy, być może będziesz musiał skopiować dane produkcyjne do tego środowiska, aby prognozy zadziałały. Model prognozy używa wielu lat danych do tworzenia prognoz. Dane demonstracyjne Contoso nie zawierają wystarczającej ilości danych historycznych do szkolenia modelu prognozy. 

## <a name="configure-your-azure-ad-tenant"></a>Konfiguracja dzierżawcy usługi Azure AD

Usługa Azure Active Directory( Azure AD) musi być tak skonfigurowana, aby można było jej używać z aplikacjami Dataverse i Microsoft Power Platform. Ta konfiguracja wymaga, by albo rola **Właściciela projektu**, albo **Menedżera środowiska** była przypisana do użytkownika w polu **Roli zabezpieczeń projektu** w usłudze LCS.

Upewnij się, że następujące ustawienia zostały zakończone:

- Masz dostęp do opcji **Administrator systemu** i **Dostosowanie systemu** w Centrum administratora programu Power Portal.
- Sprawdź, czy do użytkownika, który instaluje dodatek Finance Insights, ma zastosowanie licencja Dynamics 365 Finance lub równoważna.

Poniższe aplikacje Azure AD są zarejestrowane w usłudze Azure AD.

|  Zgłoszenie                             | Identyfikator aplikacji                               |
|------------------------------------------|--------------------------------------|
| CDS mikrousług ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 |
    
## <a name="configure-dataverse"></a>Skonfiguruj usługę Dataverse

Wykonaj następujące kroki, aby skonfigurować Dataverse for Finance Insights.

- W LCS otwórz stronę środowiska i sprawdź, czy sekcja **Integracja Power Platform** jest już skonfigurowana.

    - Jeśli usługa Dataverse jest już skonfigurowana, na liście powinna znajdować się nazwa środowiska Finance połączona ze środowiskiem Dataverse.
    - Jeśli usługa Dataverse nie jest jeszcze skonfigurowana, wybierz **Konfiguracja**. Konfiguracja środowiska Dataverse może potrwać do godziny. Po pomyślnym zakończeniu instalacji powinna zostać wyświetlona nazwa środowiska Dataverse połączonego ze środowiskiem Finance.
    - Jeśli ta integracja została ustawiona z istniejącym środowiskiem Microsoft Power Platform, skontaktuj się z administratorem, aby upewnić się, że połączone środowisko nie jest w stanie wyłączenia.

        Aby uzyskać więcej informacji, zobacz sekcję [Włączanie narzędzia integracji Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md). 

        Aby uzyskać dostęp do witryny administratora Microsoft Power Platform, przejdź do witryny <https://admin.powerplatform.microsoft.com/environments>.

## <a name="configure-the-finance-insights-add-in"></a>Konfigurowanie dodatku Finance Insights

Jeśli wcześniej został zainstalowany dodatek Finance insights, odinstaluj go przed zakończeniem następującej procedury.

> [!NOTE]
> Jeśli już zainstalowano ten dodatek Data Lake usługi LCS, program Finance insights użyje go do zapisania danych wymaganych do prognoz. Jeśli jeszcze nie zainstalowano dodatku data w u usługach LCS, dodatek Finance insights utworzy dla Ciebie zarządzany dodatek Data Lake.

Aby zainstalować dodatek Finanse Insights, należy wykonać następujące kroki.

1. Zaloguj się do LCS, a następnie w obszarze nazwy środowiska po prawej stronie strony wybierz opcję **Pełne szczegóły**.
2. W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
3. Konfigurowanie dodatku **Finance Insights**.
4. Przyjmij warunki i postanowienia, a następnie wybierz opcję **Zainstaluj**.

Instalacja dodatku może potrwać kilka minut.

## <a name="one-last-thing"></a>Ostatnia rzecz:

Po pomyślnym zainstalowaniu tego dodatku może potrwać godzinę, zanim będzie można włączyć funkcje Finance Insights w obszarze roboczym **Zarządzanie funkcjami** w programie Dynamics 365 Finance. Jeśli nie chcesz czekać tak długo, możesz ręcznie uruchomić proces sprawdzania stanu **inicjowania obsługi aplikacji Insights**. 

1. W Dynamics 365 Finance przejdź do pozycji **Administrowanie systemem \> Ustawienia \> Automatyzacja procesu**.
2. Na karcie **Procesy tła** znajdź sprawdzanie stanu udostępniania usługi **Insights** i wybierz pozycję **Edytuj**.
3. Ustaw wartość **w polu Następne wykonanie** na 30 minut przed bieżącym czasem.

   Ta zmiana powinna wymuszać natychmiastowe uruchomienie procesu sprawdzania stanu udostępniania **usługi Insights**.

   Po pomyślnym uruchomieniu procesu **sprawdzania stanu inicjowania obsługi aplikacji Insights** można włączyć funkcje aplikacji Finance Insights w obszarze roboczym **Zarządzanie funkcjami**.

> [!NOTE]
> Jeśli proces **Sprawdzania stanu konfiguracji Szczegółowych informacji** nie działa, przejdź do **Administrowania systemem** > **Zapytania** > **Zadania wsadowe**. W polu **System zgłaszania automatyzacji procesu** zmień wartość na **Oczekiwanie**, aby zainicjować proces. 
> 
## <a name="feedback-and-support"></a>Opinie i pomoc techniczna

Jeśli chcesz przekazać opinie lub potrzebujesz pomocy technicznej, wyślij e-mail do [Finance Insights (wersja zapoznawcza)](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
