---
title: Rozpoczynanie pracy z fakturowaniem elektronicznym dla Brazylii
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z funkcją Faktury elektroniczne dla Brazylii w Finance i Supply Chain Management.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f8caaa6417365a131da0565cbc4a9f79425d0c7e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840275"
---
# <a name="get-started-with-electronic-invoicing-for-brazil"></a>Rozpoczynanie pracy z fakturowaniem elektronicznym dla Brazylii 

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Brazylii. W tym temacie podasz informacje o krokach konfiguracji zależnych od kraju w Regulatory Configuration Services (RCS) i uzupełnij czynności opisane w temacie [Wprowadzenie do funckji Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja brazylijskiej funkcji fakturowania elektronicznego NF-e (BR)

Niektóre parametry dostępne w funkcji **Faktura elektroniczna brazylisjka NF-e (BR)** są publikowane z wartościami domyślnymi. Przejrzyj te wartości, a w razie potrzeby zaktualizuj je, aby lepiej odzwierciedlały operację biznesową przed wdrożeniem funkcji fakturowania elektronicznego w środowisku usługi.

Opisano w sekcji **Specyficzna dla kraju konfiguracja funkcji fakturowania elektronicznego** w tym temacie [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w obszarze **Funkcje** obszaru roboczego **Funkcja globalizacji**, wybierz kafelek **Faktury elektroniczne**.
2. Na stronie **Funkcje fakturowania elektronicznego** sprawdź, czy jest wybrana utworzona funkcja elektronicznego fakturowania **Brazylijska NF-e (BR)**.
3. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
4. Na karcie **Ustawienia** w siatce wybierz pozycję **Prześlij**, a następnie wybierz pozycję **Edytuj**.
5. Na karcie **Akcje** w grupie pól **Akcje** wybierz akcję **(wersja zapoznawcza) Podpisz dokument XML**.
6. W grupie pól **Parametry** wybierz opcję **Nazwa certyfikatu** oraz w polu **Wartość** wprowadź nazwę certyfikatu skojarzonego z parametrem klucza.
7. Na karcie **Akcje** w grupie pól **Akcje** wybierz akcję **(wersja zapoznawcza) Wywołaj brazylijską usługę SEFAZ**.
8. W grupie pól **Parametry** wybierz parametr **Adresu URL**.
9. W razie potrzeby w polu **Wartość** przejrzyj i zaktualizuj adres URL usług sieci web opublikowanych w dokumentacji SEFAZ dla swojego województwa, a następnie wybierz pozycję **Zapisz**.
10. Na karcie **Reguły możliwości zastosowania** w grupie pól **Konfiguracja reguł możliwości zastosowania** przejrzyj i zaktualizuj w razie potrzeby kryteria pola **Stan** dla tego samego stanu, do którego odnosi się adres URL usług sieci web.
11. Wybierz przycisk **Zapisz** i zamknij stronę.
12. Aby wdrożyć funkcję fakturowania elektronicznego w środowisku usługi, zobacz temat [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja konfiguracji aplikacji dla brazylijskiej funkcji fakturowania elektronicznego NF-e (BR)

Przed wdrożeniem konfiguracji aplikacji w połączonej aplikacji Finance lub Supply Chain Management wykonaj poniższe kroki.

Opisano w sekcji **Specyficzna dla kraju konfiguracja aplikacji** w tym temacie [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w obszarze **Funkcje** obszaru roboczego **Funkcja globalizacji**, wybierz kafelek **Faktury elektroniczne*.
2. Na stronie **Funkcje fakturowania elektronicznego** sprawdź, czy jest wybrana utworzona funkcja elektronicznego fakturowania **Brazylijska NF-e (BR)**.
3. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
4. Na karcie **Ustawienia** wybierz pozycję **Ustawienia aplikacji** i w polu **Połączona aplikacja** wybierz aplikację, w której chcesz wdrożyć.
5. W polu **Nazwa tabeli** i upewnij się, że jest wybrana opcja **Nagłówek dokumentu fiskalnego**.
6. Wybierz **Typy odpowiedzi**, a następnie wybierz opcję **Nowy**.
7. W polu **Typ odpowiedzi** wprowadź "Odpowiedź" jako stałą wartość, a w polu **Opis** wprowadź opis.
8. W polu **Stan przesyłania** wybierz **W trakcie**.
9. W polu **Mapowanie modelu** wybierz opcję **Mapowanie modelu z wiadomości odpowiedzi** z **(wersja zapoznawcza) Format importu wiadomości odpowiedzi**, a następnie wybierz **Zapisz**.
10. Wybierz **Nowy** w polu **Typ odpowiedzi** wprowadź "ResponseData" jako stałą wartość, a w polu **Opis** wprowadź opis.
11. W polu **Stan przesyłania** wybierz **W trakcie**.
12. W polu **Mapowanie modelu** wybierz opcję **Import danych odpowiedzi** z **(wersja zapoznawcza) Format importu danych odpowiedzi NF-e (BR)**, a następnie wybierz **Zapisz**.
13. Aby wdrożyć konfigurację aplikacji w połączonej aplikacji Finance lub Supply Chain, zobacz temat [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja brazylijskiego NFS-e ABRASF Curitiba (BR) Funkcja fakturowania elektronicznego

Niektóre parametry dostępne w funkcji **Faktura elektroniczna brazylisjka NFS-e ABRASF Curitiba (BR)** są publikowane z wartościami domyślnymi. Przejrzyj te wartości i w razie potrzeby zaktualizuj je, aby lepiej odzwierciedlały operację biznesową przed wdrożeniem funkcji fakturowania elektronicznego w środowisku usługi.

Opisano w sekcji **Specyficzna dla kraju konfiguracja funkcji fakturowania elektronicznego** w tym temacie [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w obszarze **Funkcje** obszaru roboczego **Funkcja globalizacji**, wybierz kafelek **Faktury elektroniczne**.
2. Na stronie **Funkcje fakturowania elektronicznego** sprawdź, czy jest wybrana utworzona funkcja elektronicznego fakturowania **Brazylijski NFS-e ABRASF Curitiba (BR)**.
3. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**, a następnie na karcie **Ustawienia** w siatce wybierz pozycję **Prześlij**.
4. Wybierz opcję **Edycja**, a na karcie **Akcje** w grupie pól **Akcje** wybierz pierwszą pozycję **(wersja zapoznawcza) Podpisz dokument XML**.
5. W grupie pól **Parametry** wybierz parametr **Nazwa certyfikatu**.
6. W polu **Wartość** wprowadź nazwę certyfikatu skojarzonego z parametrem klucza.
7. W grupie pól **Akcje** wybierz drugie wystąpienie dokumentu **(wersja zapoznawcza) Podpisz dokument XML**.
8. W grupie pól **Parametry** wybierz parametr **Nazwa certyfikatu**.
9. W polu **Wartość** wprowadź nazwę certyfikatu skojarzonego z parametrem klucza.
10. Na karcie **Akcje** w grupie pól **Akcje** wybierz akcję **(wersja zapoznawcza) Wywołaj brazylijską usługę SEFAZ**.
11. W grupie pól **Parametry** wybierz parametr **Adresu URL**.
12. W razie potrzeby w polu **Wartość** przejrzyj i zaktualizuj adresy URL usług internetowych opublikowanych przez wydział podatkowy miasta Kurytyba, a następnie wybierz **Zapisz**.
13. Na karcie **Ustawienia** w siatce wybierz pozycję **Zapytanie**, a następnie wybierz pozycję **Edytuj**.
14. Na karcie **Akcje** w grupie pól **Akcje** wybierz akcję **(wersja zapoznawcza) Wywołaj brazylijską usługę SEFAZ**.
15. W grupie pól **Parametry** wybierz parametr **Adresu URL**.
16. W razie potrzeby w polu **Wartość** przejrzyj i zaktualizuj adresy URL usług internetowych opublikowanych przez wydział podatkowy miasta Kurytyba.
17. Wybierz przycisk **Zapisz** i zamknij stronę.
18. Aby wdrożyć funkcję fakturowania elektronicznego w środowisku usługi, zobacz temat [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja konfiguracji aplikacji dla brazylijskiego NFS-e ABRASF Curitiba (BR) Funkcja fakturowania elektronicznego

Przed wdrożeniem konfiguracji aplikacji w połączonej aplikacji Finance lub Supply Chain Management wykonaj poniższe kroki.

Opisano w sekcji **Specyficzna dla kraju konfiguracja aplikacji** w tym temacie [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w obszarze **Funkcje** obszaru roboczego **Funkcja globalizacji**, wybierz kafelek **Faktury elektroniczne**.
2. Na stronie **Funkcje fakturowania elektronicznego** sprawdź, czy jest wybrana funkcja elektronicznego fakturowania **Brazylijski NFS-e ABRASF Curitiba (BR)**.
3. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**, a następnie na karcie **Ustawienia** wybierz pozycję **Konfiguracja aplikacji**.
4. W polu **Połączona aplikacja** wybierz aplikację, w której chcesz wdrożyć.
5. W **Nazwa tabeli** sprawdź, czy wybrany jest nagłówek dokumentu fiskalnego.
6. Wybierz **Typy odpowiedzi** i wybierz opcję **Nowy**.
7. W polu **Typ odpowiedzi** wprowadź "ABRASFCuritibaSubmitResponse" jako stałą wartość, a w polu **Opis** wprowadź opis.
8. W polu **Stan przesyłania** wybierz **W trakcie**.
9. W polu **Mapowanie modelu** wybierz opcję **Import wiadomości z odpowiedzią** z **(wersja zapoznawcza) Import wiadomości odpowiedzi NFS-e ABRASF Curitiba (BR)**, a następnie wybierz **Zapisz**.
10. Wybierz **Nowy** w polu **Typ odpowiedzi** wprowadź "ABRASFCuritibaSubmitResponseData" jako stałą wartość, a w polu **Opis** wprowadź opis.
11. W polu **Stan przesyłania** wybierz **W trakcie**.
12. W polu **Mapowanie modelu** wybierz opcję **Import danych odpowiedzi** z **(wersja zapoznawcza) Format importu danych odpowiedzi NFS-e ABRASF (BR)**, a następnie wybierz **Zapisz**.
13. Wybierz **Nowy** w polu **Typ odpowiedzi** wprowadź "ABRASFCuritibaInquireResponse" jako stałą wartość, a w polu **Opis** wprowadź opis.
14. W polu **Stan przesyłania** wybierz **W trakcie**.
15. W polu **Mapowanie modelu** wybierz opcję **Import wiadomości z odpowiedzią** z **(wersja zapoznawcza) Import wiadomości odpowiedzi NFS-e ABRASF Curitiba (BR).**
16. Wybierz przycisk **Zapisz** i zamknij stronę.
17. Aby wdrożyć konfigurację aplikacji w połączonej aplikacji Finance lub Supply Chain, zobacz temat [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Klauzula prywatności
Włączenie funkcji **NF-e federalna - brazylijska faktura elektroniczna (BR)** i **NFS-e - brazylijska faktura elektroniczna za usługę (miasto)** może wymagać przesłania ograniczonych danych, w tym numeru identyfikacji podatkowej organizacji. Dane zostaną przekazane agencjom zewnętrznym upoważnionym przez organ podatkowy w celu wysyłania faktur elektronicznych do tego organu podatkowego w predefiniowanym formacie wymaganym do integracji z rządową usługą internetową. Administrator może włączyć lub wyłączyć funkcje faktur elektronicznych **NF-e federalne - Brazylijskie faktury elektroniczne (BR)** and the **brazylijska faktura elektroniczna za usługę (miasto)**. Poniższe kroki pokazują, jak to zrobić: 

1. Przejdź do **Administrowanie organizacją** > **Konfiguracja** > **Parametry dokumentu elektronicznego**. 
2. Na karcie **Funkcje** wybierz wiersz zawierający funkcję **NF-e federalne - Brazylijska faktura elektroniczna (BR)** lub **NFS-e - brazylijska faktura elektroniczna za usługę (miasto)** i wybierz funkcję. Dane importowane z tych zewnętrznych systemów do tej usługi online Dynamics 365 podlegają naszym [oświadczeniom o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcjami Uwagi dotyczące prywatności w dokumentacji funkcji dla danego kraju.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami](e-invoicing-get-started-service-administration.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
