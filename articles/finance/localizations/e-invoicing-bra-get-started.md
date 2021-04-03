---
title: Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Brazylii
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Brazylii w Finance i Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: eaf9433ad2d9ccf3d3c5632d0f2d4fe772ff8bde
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592677"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Brazylii 

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób rozpoczęcia pracy z dodatkiem Faktur elektronicznych dla Brazylii. W tym temacie uzyskasz informacje o krokach konfiguracji zależnych od kraju w Regulatory Configuration Services (RCS) i uzupełnij czynności opisane w temacie [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja brazylijskiej funkcji fakturowania elektronicznego NF-e (BR)

Skonfigurowanie funkcji elektronicznego fakturowania brazylijskiego NF-e (BR) wymaga, aby zostały wykonane określone kroki. Niektóre parametry z konfiguracji są publikowane z wartościami domyślnymi, więc należy je przejrzeć i zaktualizować, aby lepiej pasowały do operacji biznesowej.

### <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem procedury opisanej w tej sekcji utwórz brazylijską funkcję fakturowania elektronicznego NF-e (BR) dla swojej organizacji, jak opisano w **Tworzenie faktur elektronicznych w sekcji Dostawca organizacji** w [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w sekcji **Funkcje** obszaru roboczego **funkcji Globalizacja** wybierz kafelek **dodatku Fakturowanie elektroniczne**.
2. Na stronie **Funkcje dodawania fakturowania elektronicznego** sprawdź, czy jest wybrana utworzona funkcja elektronicznego fakturowania **Brazylijska NF-e (BR)**.
3. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
4. Na karcie **Ustawienia** w siatce wybierz pozycję **Prześlij**, a następnie wybierz pozycję **Edytuj**.
5. Na karcie **Akcje** w grupie pól **Akcje** wybierz akcję **(wersja zapoznawcza) Podpisz dokument XML**.
6. W grupie pól **Parametry** wybierz opcję **Nazwa certyfikatu** oraz w polu **Wartość** wprowadź nazwę certyfikatu skojarzonego z parametrem klucza.
7. Na karcie **Akcje** w grupie pól **Akcje** wybierz akcję **(wersja zapoznawcza) Wywołaj brazylijską usługę SEFAZ**.
8. W grupie pól **Parametry** wybierz parametr **Adresu URL**.
9. W razie potrzeby w polu **Wartość** przejrzyj i zaktualizuj adres URL usług sieci web opublikowanych w dokumentacji SEFAZ dla swojego województwa, a następnie wybierz pozycję **Zapisz**.
10. Na karcie **Reguły możliwości zastosowania** w grupie pól **Konfiguracja reguł możliwości zastosowania** przejrzyj i zaktualizuj w razie potrzeby kryteria pola **Stan** dla tego samego stanu, do którego odnosi się adres URL usług sieci web.
11. Wybierz przycisk **Zapisz** i zamknij stronę.
12. Aby skonfigurować konfigurację aplikacji, zobacz temat [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja konfiguracji aplikacji dla brazylijskiej funkcji fakturowania elektronicznego NF-e (BR)

Skonfigurowanie konfiguracji aplikacji dla brazylijskiej funkcji fakturowania elektronicznego NF-e (BR) wymaga wykonania określonych czynności. Należy ukończyć te czynności przed wdrożeniem funkcji Fakturowanie elektroniczne w środowisku usługi dodatku Fakturowanie elektroniczne.

### <a name="prerequisites"></a>Wymagania wstępne

Przed zakończeniem procedury w tej sekcji utwórz i **Zainicjuj konfigurację aplikacji** funkcji fakturowania elektronicznego brazylijskiego NF-e (BR) zgodnie z opisem w [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w sekcji **Funkcje** obszaru roboczego **funkcji Globalizacja** wybierz kafelek **dodatku Fakturowanie elektroniczne**.
2. Na stronie **Funkcje dodawania fakturowania elektronicznego** sprawdź, czy jest wybrana utworzona funkcja elektronicznego fakturowania **Brazylijska NF-e (BR)**.
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
13. Aby wdrożyć funkcję fakturowania elektronicznego, zobacz temat [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja brazylijskiego NFS-e ABRASF Curitiba (BR) Funkcja fakturowania elektronicznego

Konfiguracja brazylijskiej funkcji fakturowania elektronicznego NFS-e ABRASF Curitiba (BR) wymaga wykonania określonych czynności. Niektóre parametry z konfiguracji są publikowane z wartościami domyślnymi, więc należy je przejrzeć i zaktualizować, aby lepiej pasowały do operacji biznesowej.

### <a name="prerequisites"></a>Wymagania wstępne

Przed zakończeniem procedury opisanej w tej sekcji utwórz funkcję fakturowania elektronicznego brazylijskiego NFS-e ABRASF Curitiba (BR) w swojej organizacji. Opisano w sekcji **Konfigurowanie funkcji fakturowania elektronicznego** w tym temacie [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w sekcji **Funkcje** obszaru roboczego **funkcji Globalizacja** wybierz kafelek **dodatku Fakturowanie elektroniczne**.
2. Na stronie **Funkcje dodawania fakturowania elektronicznego** sprawdź, czy jest wybrana utworzona funkcja elektronicznego fakturowania **Brazylijski NFS-e ABRASF Curitiba (BR)**.
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
18. Aby skonfigurować konfigurację aplikacji, zobacz temat [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja konfiguracji aplikacji dla brazylijskiego NFS-e ABRASF Curitiba (BR) Funkcja fakturowania elektronicznego

Skonfigurowanie konfiguracji aplikacji dla brazylijskiego NFS-e ABRASF Curitiba (BR) Funkcja fakturowania elektronicznego wymaga wykonania określonych czynności przed wdrożeniem funkcji fakturowania elektronicznego w dodatkowym środowisku usługi Fakturowanie elektroniczne.

### <a name="prerequisites"></a>Wymagania wstępne

Przed zakończeniem procedury w tej sekcji utwórz i zainicjuj funkcję fakturowania elektronicznego brazylijskiego NFS-e ABRASF Curitiba (BR) zgodnie z opisem w sekcji **Skonfiguruj ustawienia aplikacji** w temacie [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md).

1. W RCS w sekcji **Funkcje** obszaru roboczego **funkcji Globalizacja** wybierz kafelek **dodatku Fakturowanie elektroniczne**.
2. Na stronie **Funkcje dodawania fakturowania elektronicznego** sprawdź, czy jest wybrana funkcja elektronicznego fakturowania **Brazylijski NFS-e ABRASF Curitiba (BR)**.
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
16. Wybierz **Zapisz** i wróć do tematu [Wprowadzenie do dodatku Fakturowanie elektroniczne](e-invoicing-get-started.md), aby wdrożyć funkcję Fakturowania elektrycznego.

## <a name="privacy-notice"></a>Klauzula prywatności
Włączenie funkcji **NF-e federalna - brazylijska faktura elektroniczna (BR)** i **NFS-e - brazylijska faktura elektroniczna za usługę (miasto)** może wymagać przesłania ograniczonych danych, w tym numeru identyfikacji podatkowej organizacji. Dane zostaną przekazane agencjom zewnętrznym upoważnionym przez organ podatkowy w celu wysyłania faktur elektronicznych do tego organu podatkowego w predefiniowanym formacie wymaganym do integracji z rządową usługą internetową. Administrator może włączyć lub wyłączyć funkcje faktur elektronicznych **NF-e federalne - Brazylijskie faktury elektroniczne (BR)** and the **brazylijska faktura elektroniczna za usługę (miasto)**. Poniższe kroki pokazują, jak to zrobić: 

1. Przejdź do **Administrowanie organizacją** > **Konfiguracja** > **Parametry dokumentu elektronicznego**. 
2. Na karcie **Funkcje** wybierz wiersz zawierający funkcję **NF-e federalne - Brazylijska faktura elektroniczna (BR)** lub **NFS-e - brazylijska faktura elektroniczna za usługę (miasto)** i wybierz funkcję. Dane importowane z tych zewnętrznych systemów do tej usługi online Dynamics 365 podlegają naszym [oświadczeniom o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcjami Uwagi dotyczące prywatności w dokumentacji funkcji dla danego kraju.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie dodatku do fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z dodatkiem do fakturowania elektronicznego — administrowanie usługami](e-invoicing-get-started-service-administration.md)
- [Rozpoczynanie pracy z dodatkiem fakturowania elektronicznego](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
