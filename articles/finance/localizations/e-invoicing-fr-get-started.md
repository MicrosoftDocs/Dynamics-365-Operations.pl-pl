---
title: Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Francji
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Francji.
author: dkalyuzh
ms.date: 07/07/2022
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-00-02
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: 3ac4af8c131e35d9a499d0d558c7cce1d4872b37
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573286"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-france"></a>Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Francji

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Francji. Ten artykuł przeprowadzi Cię przez kolejne kroki konfiguracji, które są zależne od kraju/regionu, w usługach Regulatory Configuration Service (RCS). Te kroki uzupełniają kroki opisane w artykule [Rozpoczynanie pracy z dodatkiem fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Konfiguracja specyficzna dla kraju dla francuskiego zgłaszania Chorus Pro (FR) Funkcja fakturowania elektronicznego

Aby skonfigurować **Francuskie zgłaszanie Chorus Pro (FR)** funkcję fakturowania elektronicznego, należy wykonać pewne czynności. Niektóre parametry z konfiguracji są publikowane z wartościami domyślnymi. Wartości te należy przeglądać i aktualizować, aby lepiej odzwierciedlały one operacje biznesowe.

### <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem procedur opisanych w tym artykule należy spełnić następujące wymagania wstępne:

- Zapoznaj się z informacjami o fakturowaniu elektronicznym. Aby uzyskać więcej informacji, zajrzyj do [Omówienie fakturowania elektronicznego](e-invoicing-service-overview.md).
- Zarejestruj się w RCS i skonfiguruj fakturowanie elektroniczne. Aby uzyskać więcej informacji, zobacz następujące artykuły:

    - [Zarejestruj się i zainstaluj usługę fakturowania elektronicznego](e-invoicing-sign-up-install.md)
    - [Ustawianie zasobów systemu Azure dla fakturowania elektronicznego](e-invoicing-set-up-azure-resources.md)
    - [Zainstaluj dodatek dla mikrousług w Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    - [Aktywuj i skonfiguruj integrację z fakturowaniem elektronicznym](e-invoicing-activate-setup-integration.md) — Skorzystaj z informacji zawartych w tym artykule, aby aktywować integrację między aplikacją Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management a aplikacją Electronic Usługa fakturowania.
    - [Kody NAF i numery Siret](emea-fra-naf-codes-siret-numbers.md) oraz [Ustaw kody NAF i numery Siret](tasks/fr-00003-naf-codes-siret-numbers.md) — te informacje są podane w tych artykułach do skonfigurowania kodów NAF i numerów Siret w firmach. 

- Firma musi być zarejestrowana do działalności w firmie Chorus Pro. Microsoft zapewnia integrację z Chorus pro w trybie OAuth2 za pośrednictwem interfejsu programowania aplikacji (API). Szczegółowe informacje na temat rejestracji i aktywacji aplikacji Chorus Pro można znaleźć w dokumentacji [oficjalnej](https://communaute.chorus-pro.gouv.fr/documentation/help-for-api-developers-in-oauth2-mode/).

    Wykonaj poniższe czynności, aby zarejestrować się w Chorus Pro.

    1. Przejdź do [portalu PISTE](https://piste.gouv.fr/en/component/apiportal/registration), aby rozpocząć rejestrację. 
    2. Zarejestruj aplikację i aktywuj poświadczenia Open Authorization (OAuth).
    3. Skopiuj i zapisz identyfikator klienta dla poświadczeń OAuth i klucza tajnego. Informacje te zostaną podane w kolejnych krokach.
    4. Przejdź do [portalu Chorus Pro,](https://portail.chorus-pro.gouv.fr/aife_csm/?id=aife_enrollment) aby zarejestrować. 
    5. Utwórz konto techniczne na celu dostęp do interfejsu API. Aby uzyskać więcej informacji, zobacz temat [Tworzenie konta technicznego dla dostępu interfejsu API w środowisku produkcyjnym](https://communaute.chorus-pro.gouv.fr/documentation/creation-of-a-technical-account-for-an-api-access-in-production/).
    6. Skopiuj identyfikator użytkownika konta technicznego i hasło. Informacje te zostaną podane w kolejnych krokach.

## <a name="country-specific-configuration-of-the-application-setup-for-the-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja konfiguracji aplikacji dla francuskiego zgłaszania Chorus Pro (FR) Funkcja fakturowania elektronicznego

Niektóre parametry dostępne w funkcji **Francuskie zgłoszenie Chorus Pro (FR)** są publikowane z wartościami domyślnymi. Przed wdrożeniem funkcji fakturowania elektronicznego w środowisku usługi przejrzyj wartości domyślne i zaktualizuj je zgodnie z wymaganiami, aby lepiej odzwierciedlały Twoją działalność biznesową.

1. W magazynie Azure key vault utwórz wpisy tajne i odpowiednie odwołanie do nich. Aby uzyskać więcej informacji, zobacz temat [Certyfikaty i klucze tajne klienta](e-invoicing-customer-certificates-secrets.md).
2. Zaimportuj najnowszą wersję funkcję globalizacji **Francuskie zgłoszenie Chorus Pro (FR)** zgodnie z opisem w [Importuj funkcje z globalnego repozytorium](e-invoicing-import-feature-global-repository.md).
3. Utwórz kopię zaimportowanych funkcji globalizacji i wybierz dostawcę konfiguracji. Aby uzyskać więcej informacji, zobacz [Tworzenie funkcji globalizacji](e-invoicing-create-new-globalization-feature.md).
4. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
5. Na karcie **Ustawienia** w siatce wybierz ustawienia funkcji **Faktury sprzedaży UBL**.
6. Wybierz **pozycję Edytuj**, a następnie, na karcie **Potok przetwarzania**, w sekcji **Przetwarzanie potoku** wybierz **opcję (Podgląd) Integruj z francuskim Chorus Pro** o nazwie akcji **Przesłanie za pomocą francuskiego Chorus Pro**.
7. W sekcji **Parametry** w polu **Tajny nazwa identyfikatora klienta** wybierz tajny identyfikator utworzony dla identyfikatora klienta w kluczu.
8. W polu **Tajna nazwa klienta** wybierz tajną nazwę utworzoną dla klucza tajnego klienta w magazynie kluczy.
9. W polu **Nazwa tajna logowania technicznego** wybierz tajną nazwę utworzoną do logowania na konto techniczne w magazynie kluczy.
10. W polu **Tajna nazwa hasła technicznego** wybierz tajną nazwę utworzoną do hasła na konto techniczne w magazynie kluczy.
11. Na karcie **Potok przetwarzania**, w sekcji **Przetwarzanie potoku** wybierz opcję **Integruj z francuskim Chorus Pro** o nazwie akcji **Status wniosku francuskiego Chorus Pro**.
12. W sekcji **Parametry** w polu **Tajny nazwa identyfikatora klienta** wybierz tajny identyfikator utworzony dla identyfikatora klienta w kluczu.
13. W polu **Tajna nazwa klienta** wybierz tajną nazwę utworzoną dla klucza tajnego klienta w magazynie kluczy.
14. W polu **Nazwa tajna logowania technicznego** wybierz tajną nazwę utworzoną do logowania na konto techniczne w magazynie kluczy.
15. W polu **Tajna nazwa hasła technicznego** wybierz tajną nazwę utworzoną do hasła na konto techniczne w magazynie kluczy.
16. Wybierz przycisk **Zapisz** i zamknij stronę.
17. Powtórz kroki od 6 do 16 dla konfiguracji elementu na podstawie **faktury projektu UBL na podstawie**, konfiguracji elementu **na podstawie faktury projektu UBL na podstawie** i **konfiguracji elementu na podstawie faktury projektu UBL**.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie dodatku do fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z dodatkiem do fakturowania elektronicznego — administrowanie usługami](e-invoicing-get-started-service-administration.md)
- [Rozpoczynanie pracy z dodatkiem fakturowania elektronicznego](e-invoicing-get-started.md)
