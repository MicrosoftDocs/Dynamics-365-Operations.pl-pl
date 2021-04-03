---
title: Rozpoczynanie pracy z dodatkiem fakturowania elektronicznego dla Egiptu
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Egiptu w Finance i Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/26/2021
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
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 68ee08226f440e850a080600dbf5e16768b45e43
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592605"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-egypt"></a>Rozpoczynanie pracy z dodatkiem fakturowania elektronicznego dla Egiptu

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Egiptu. W tym temacie podasz informacje o krokach konfiguracji zależnych od kraju w Regulatory Configuration Services (RCS) i uzupełnij czynności opisane w temacie [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja egipskiej faktury elektronicznej (EG) Funkcja fakturowania elektronicznego

Aby skonfigurować egipską fakturę elektroniczną (EG), należy wykonać kilka czynności. Niektóre parametry z konfiguracji są publikowane z wartościami domyślnymi, więc należy je przejrzeć i zaktualizować, aby lepiej pasowały do operacji biznesowej.

### <a name="prerequisites"></a>Wymagania wstępne

Przed zakończeniem procedury opisanej w tej sekcji musisz:

- Utwórz tajny kod certyfikatu cyfrowego w sposób opisany w temacie **Tworzenie tajnej sekcji certyfikatu cyfrowego** w temacie [Wprowadzenie do administrowania usługą dodatku Fakturowanie elektroniczne](e-invoicing-get-started-service-administration.md). Do celów testowych egipski urząd skarbowy zapewnia specjalne testowe certyfikaty cyfrowe, których należy używać tylko na etapie testowania i weryfikacji rozwiązania. Aby uzyskać więcej informacji, odwiedź witrynę internetową egipskiego organu podatkowego, korzystając z łącza znajdującego się w [Egipskim zestawie SDK do e-fakturowania](https://sdk.sit.invoicing.eta.gov.eg/faq/).
- Utwórz egipską fakturę elektroniczną (EG) Funkcja fakturowania elektronicznego dla swojej organizacji, zgodnie z opisem w sekcji **Tworzenie faktur elektronicznych w sekcji Dostawca organizacji** w [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w sekcji **Funkcje** obszaru roboczego **funkcji Globalizacja** wybierz kafelek **dodatku Fakturowanie elektroniczne**.
2. Na stronie **Funkcje dodawania fakturowania elektronicznego** sprawdź, czy jest wybrana utworzona funkcja elektronicznego fakturowania **Egipska faktura elektroniczna (EG)**.
3. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
4. Na karcie **Ustawienia** w siatce wybierz ustawienia funkcji **Faktury sprzedaży**.
5. Wybierz opcję **Edycja**, a na karcie **Akcje** w grupie pól **Akcje** wybierz pozycję **Podpisz dokument JSON dla urzędu skarbowego**.
6. W grupie pól **Parametry** wybierz parametr, **Nazwa certyfikatu** i wybierz nazwę certyfikatu cyfrowego utworzonego do używania z funkcją fakturowania elektronicznego.
7. W grupie pól **Akcje** wybierz opcję **Integruj z usługą ETA**. Powtórz ten krok dla dwóch wystąpień tej akcji.
8. W grupie pól **Parametry** wybierz **Adres URL usługi sieci Web** i **Adres URL usługi logowania** oraz w razie potrzeby przejrzyj parametry adresu URL. Odwiedź witrynę egipskiego urzędu skarbowego, aby uzyskać adres URL do testowania i produkcji, korzystając z linku podanego w [Egipskim zestawie SDK do e-fakturowania](https://sdk.sit.invoicing.eta.gov.eg/faq/).
9. Wybierz przycisk **Zapisz** i zamknij stronę.
10. Aby skonfigurować konfigurację aplikacji, zobacz temat [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-the-application-setup-for-the-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja konfiguracji aplikacji dla egipskiej faktury elektronicznej (EG) Funkcja fakturowania elektronicznego

Konfiguracja konfiguracji aplikacji dla **Egipskiej faktury elektronicznej (EG) Funkcja fakturowania elektronicznego** wymaga wykonania określonych czynności. Należy wykonać te czynności przed wdrożeniem funkcji Fakturowanie elektroniczne w środowisku usługi dodatku Fakturowanie elektroniczne.

### <a name="prerequisites"></a>Wymagania wstępne

Przed zakończeniem procedury opisanej w tej sekcji utwórz i zainicjuj **Egipską fakturę elektroniczną (EG)** Funkcja fakturowania elektronicznego, aby skonfigurować ustawienia aplikacji dla **Egipskiej faktury elektronicznej (EG)** Funkcja fakturowania elektronicznego, zgodnie z opisem w sekcji **Konfigurowanie konfiguracji aplikacji** w temacie [Zacznij korzystać z dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w sekcji **Funkcje** obszaru roboczego **funkcji Globalizacja** wybierz kafelek **dodatku Fakturowanie elektroniczne**.
2. Na stronie **Funkcje dodawania fakturowania elektronicznego** sprawdź, czy jest wybrana utworzona funkcja elektronicznego fakturowania **Egipska faktura elektroniczna (EG)**.
3. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
4. Na karcie **Ustawienia** wybierz pozycję **Ustawienia aplikacji** i w polu **Połączona aplikacja** wybierz aplikację, w której chcesz wdrożyć.
5. Sprawdź, czy jest wybrany arkusz faktur dla odbiorcy, w polu **Nazwa tabeli**.
6. Wybierz **Typy odpowiedzi**, a następnie wybierz opcję **Nowy**.
7. W polu **Typ odpowiedzi** wprowadź odpowiedź, a w polu **Opis** wprowadź opis.
8. W polu **Stan przesyłania** wybierz **W trakcie**.
9. W polu **Mapowanie modelu** wybierz opcję **Mapowanie modelu z wiadomości odpowiedzi** z **(wersja zapoznawcza) Format importu wiadomości odpowiedzi**, a następnie wybierz **Zapisz**.
10. Wybierz **Nowe** i następnie w polu **Typ odpowiedzi** wprowadź „ResponseData” jako stałą wartość. W polu **Opis** wprowadź „Opis”.
11. W polu **Stan przesyłania** wybierz **W trakcie**.
12. W polu **Nazwa jednostki danych** wybierz pozycję **Nagłówki faktur sprzedaży w wersji 2**.
13. W polu **Mapowanie modelu** wybierz opcję **Import danych odpowiedzi z Egiptu** z **(wersja zapoznawcza) Import danych odpowiedzi z Egiptu**, a następnie wybierz **Zapisz**.
14. Aby wdrożyć funkcję fakturowania elektronicznego, zobacz temat [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Klauzula prywatności

Włączenie i używanie funkcji **Egipska faktura elektroniczna (EG)** może wymagać przesłania ograniczonych danych, w tym numeru identyfikacji podatkowej organizacji. Dane te zostaną przekazane zewnętrznym agencjom upoważnionym przez organ podatkowy w celu wysyłania faktur elektronicznych do tego organu podatkowego w predefiniowanym formacie wymaganym do integracji z rządowym serwisem internetowym. Administrator może włączyć lub wyłączyć funkcję, przechodząc do **Administrowanie organizacją** > **Konfiguracja** > **Parametry dokumentu elektronicznego**. Wybierz kartę **Funkcje**, wybierz wiersze zawierające funkcję **Egipska faktura elektroniczna (EG)** a następnie dokonaj odpowiedniego wyboru. Dane importowane z tych zewnętrznych systemów do tej usługi online Dynamics 365 podlegają naszym [oświadczeniom o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcjami Uwagi dotyczące prywatności w dokumentacji funkcji dla danego kraju.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie dodatku do fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z dodatkiem do fakturowania elektronicznego — administrowanie usługami](e-invoicing-get-started-service-administration.md)
- [Rozpoczynanie pracy z dodatkiem fakturowania elektronicznego](e-invoicing-get-started.md)
- [Faktury elektroniczne odbiorcy w Egipcie](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
