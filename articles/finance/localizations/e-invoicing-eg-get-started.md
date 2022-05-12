---
title: Fakturowanie elektroniczne dla Egiptu
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Egiptu w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: e21c4ce4d676c3194665672a078dc1e3d0492799
ms.sourcegitcommit: 5f7177b9ab192b5a6554bfc2f285f7cf0b046264
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661730"
---
# <a name="electronic-invoicing-for-egypt"></a>Fakturowanie elektroniczne dla Egiptu

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Egiptu. Ten artykuł przeprowadzi Cię przez kolejne kroki konfiguracji, które są zależne od kraju/regionu, w usługach Regulatory Configuration Service (RCS). Te kroki uzupełniają kroki opisane w artykule [Set up Electronic invoicing](e-invoicing-set-up-overview.md).

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem procedur opisanych w tym temacie należy spełnić następujące wymagania wstępne:

- Zapoznaj się z omówieniem fakturowania elektronicznego w sposób opisany [w temacie Fakturowanie elektroniczne](e-invoicing-service-overview.md).
- Zarejestruj się w RCS i skonfiguruj fakturowanie elektroniczne. Aby uzyskać więcej informacji, zobacz następujące tematy:

    - [Zarejestruj się i zainstaluj usługę fakturowania elektronicznego](e-invoicing-sign-up-install.md)
    - [Ustawianie zasobów systemu Azure dla fakturowania elektronicznego](e-invoicing-set-up-azure-resources.md)
    - [Zainstaluj dodatek dla mikrousług w Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    
- Uaktywnij integrację między firmą Microsoft Dynamics 365 Finance lub aplikacją Dynamics 365 Supply Chain Management a usługą fakturowania elektronicznego, jak opisano w temacie [Aktywuj i skonfiguruj integrację z fakturowaniem elektronicznym](e-invoicing-activate-setup-integration.md).
- Utwórz tajny klucz certyfikatu cyfrowego w kluczu Azure Key, a następnie skonfiguruj go w sposób [opisany w certyfikatach odbiorcy](e-invoicing-customer-certificates-secrets.md). Do celów testowych egipski urząd skarbowy zapewnia specjalne testowe certyfikaty cyfrowe, których należy używać tylko na etapie testowania i weryfikacji rozwiązania. Aby uzyskać więcej informacji, odwiedź witrynę internetową egipskiego organu podatkowego, korzystając z łącza znajdującego się w [Egipskim zestawie SDK do e-fakturowania](https://sdk.invoicing.eta.gov.eg/faq/).

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-feature"></a>Specyficzna dla kraju konfiguracja egipskiej faktury elektronicznej (EG) Funkcja fakturowania elektronicznego

Niektóre parametry dostępne w funkcji **Faktura elektroniczna Elektroniczna (EGIPT)** są publikowane z wartościami domyślnymi. Przed wdrożeniem funkcji fakturowania elektronicznego w środowisku usługi przejrzyj wartości domyślne i zaktualizuj je zgodnie z wymaganiami, aby lepiej odzwierciedlały Twoją działalność biznesową.

1. Zaimportuj najnowszą wersję **Egipskiej faktury elektronicznej (EG)** Funkcja globalizacji zgodnie z opisem w [Importuj funkcje z globalnego repozytorium](e-invoicing-import-feature-global-repository.md).
2. Utwórz kopię zaimportowanych funkcji globalizacji i wybierz dla niego dostawcę konfiguracji, zgodnie z opisem w tece [Tworzenie funkcji globalizacji](e-invoicing-create-new-globalization-feature.md).
3. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
4. Na karcie **Ustawienia** w siatce wybierz ustawienia funkcji **Faktury sprzedaży**.
5. Wybierz opcję **Edycja**.
6. Na karcie **Przetwarzanie** w sekcji **Przetwarzanie** wybierz **Podpisz dokument json dla egipskiego urzędu podatkowego**.
7. W sekcji **Parametry** wybierz nazwę **certyfikatu**, a następnie wybierz nazwę utworzonego certyfikatu cyfrowego.
8. W grupie pól **Potok przetwarzania** wybierz opcję **Integruj z usługą ETA**. Powtórz ten krok dla dwóch wystąpień tej akcji.
9. W sekcji **Parametry** wybierz **Adres URL usługi internetowej** i **Adres URL usługi logowania**. Następnie przejrzyj parametry adresu URL. Aby uzyskać testowy i produkcyjny adres URL, przejdź do witryny egipskiego urzędu skarbowego, korzystając z podanego linku w [Egipskim zestawie SDK do e-fakturowania](https://sdk.invoicing.eta.gov.eg/faq/).
10. Wybierz przycisk **Zapisz** i zamknij stronę.
11. Powtórz kroki od 4 do 10 w przypadku konfiguracji **funkcji faktur pochodnych** projektu.

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-application-setup"></a>Konfiguracja specyficzna dla kraju dla konfiguracji aplikacji egipskiej faktury elektronicznej (EG)

Istnieją parametry, które należy skonfigurować w środowisku zarządzania finansami lub Supply Chain Management. Konfigurację można zakończyć w jednym z dwóch miejsc:

- Zaloguj się do wystąpienia finansów lub Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Konfiguracja parametrów fakturowania elektronicznego](e-invoicing-set-up-parameters.md).
- W usłudze RCS. W konfiguracji dotyczącej funkcji fakturowania elektronicznego można definiować wszystkie parametry, a następnie wdrażać je bezpośrednio w środowisku zarządzania finansami lub Supply Chain Management podczas wdrażania funkcji fakturowania elektronicznego.

W przypadku obu opcji parametry są identyczne. Jeśli skonfigurujemy pierwszą funkcję w usłudze fakturowania elektronicznego, zaleca się, aby wykonać następujące kroki, aby skonfigurować parametry w zerowych systemach RCS, a następnie wdrożyć je w połączonej aplikacji.

> [!NOTE]
> Niektóre wersje funkcji fakturowania elektronicznego mogą zawierać wstępnie zdefiniowany zestaw parametrów specyficznych dla aplikacji dla zarządzania finansami lub Supply Chain Management. W tym przypadku należy sprawdzić poprawność danych. W przeciwnym razie należy ręcznie ustawić parametry.

1. Znajdź kopię utworzonej przez siebie funkcji **Egipskiej faktury elektronicznej (EG)**.
2. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
3. Na karcie **Konfiguracje** wybierz opcję **Ustawienia aplikacji**.
4. W polu **Połączone aplikacje** wybierz aplikację, w której chcesz wdrożyć.
5. Na stronie **Typy dokumentów elektronicznych** wybierz pozycję **Dodaj**, aby utworzyć rekord.
6. W polu **Nazwa tabeli** dodaj pozycję **CustInvoiceJour**.
7. W polu **Kontekst** dodaj odwołanie do nazwy **mapowania kontekstu faktury** dla odbiorcy. Konfiguracja jest modelem **kontekstu faktury dla odbiorcy**.
8. W polu **Elektroniczne mapowanie dokumentów** dodaj odwołanie do nazwy **mapowania faktury** dla odbiorcy. Konfiguracja to **Mapowanie modelu faktury**.
9. Wybierz opcję **Zapisz**.
10. Na **stronie Typy** odpowiedzi wybierz pozycję **Dodaj**.
11. W polu **typu odpowiedzi** wprowadź **Odpowiedź**.
12. W polu **Opis** wprowadź **Odpowiedź procesu**.
13. W polu **Stan przesyłania** wybierz **W trakcie**.
14. W polu **Mapowania modelu** wybierz opcję **Import wiadomości odpowiedzi**. Konfiguracją jest import **komunikatów odpowiedzi egiptu (EG)**.
15. Wybierz opcję **Zapisz**.
16. Wybierz opcję **Dodaj**.
17. W polu **typu odpowiedzi** wprowadź **ResponseData**.
18. W polu **Opis** wprowadź **Przetwarzaj dane odpowiedzi**.
19. W polu **Stan przesyłania** wybierz **W trakcie**.
20. W polu **Nazwa jednostki danych** wybierz pozycję **SalesInvoiceHeaderV2Entity**.
21. W polu **Mapowania modelu** wybierz opcję **Import danych odpowiedzi**. Konfiguracją jest import **Format importu danych odpowiedzi w Egipcie (EG)**.
22. Wybierz przycisk **Zapisz** i zamknij stronę.
23. Zamknij stronę.

Aby wdrożyć funkcję w środowisku usług i konfigurację aplikacji w połączonej aplikacji Zarządzanie finansami lub Supply Chain Management, zobacz [Temat Zakończenie, publikowanie i wdrażanie funkcji globalizacji](e-invoicing-complete-publish-deploy-globalization-feature.md)

## <a name="privacy-notice"></a>Klauzula prywatności

Włączenie funkcji **Egipska faktura elektroniczna (EG)** może wymagać wysyłania ograniczonej ilości danych. Te dane obejmują identyfikator podatkowy organizacji. Dane będą przesyłane do agencji zewnętrznych, które zostały upoważnione przez organ podatkowy do wysyłania faktur elektronicznych do tego organu podatkowego we wstępnie zdefiniowanym formacie, który jest wymagany do integracji z rządową usługą internetową. Administrator może włączyć lub wyłączyć funkcję, przechodząc do **Administrowanie organizacją** \> **Konfiguracja** \> **Parametry dokumentu elektronicznego**. Wybierz kartę **Funkcje**, wybierz wiersze zawierające funkcję **Egipska faktura elektroniczna (EG)** a następnie dokonaj odpowiedniego wyboru. Dane importowane z tych systemów zewnętrznych do tej usługi online, która wchodzi w skład usługi Dynamics 365, podlegają naszemu [oświadczeniu o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcją „Uwagi dotyczące prywatności” w dokumentacji funkcji specyficznej dla kraju.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami](e-invoicing-get-started-service-administration.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md)
- [Faktury elektroniczne odbiorcy w Egipcie](emea-egy-e-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
