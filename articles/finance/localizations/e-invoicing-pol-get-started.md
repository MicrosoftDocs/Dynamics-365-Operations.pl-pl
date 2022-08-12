---
title: Fakturowanie elektroniczne dla Polski
description: Ten artykuł zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Polski w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: ilkond
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 574537
ms.assetid: ''
ms.search.region: Poland
ms.author: janeaug
ms.search.validFrom: 2022-07-15
ms.dyn365.ops.version: AX 10.0.28
ms.openlocfilehash: ff7a7650187f120b9dbcba1e24aa67130773db04
ms.sourcegitcommit: ccaeb71c49cd15be472a3fb1c55fc655e133dc29
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2022
ms.locfileid: "9127995"
---
# <a name="get-started-with-electronic-invoicing-for-poland"></a>Zacznij korzystać z elektronicznego fakturowania w Polsce

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Polski. Przeprowadza użytkownika przez kolejne etapy konfiguracji, które są zależne od kraju w usługach Regulatory Configuration Service (RCS) w Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management. Te kroki uzupełniają kroki opisane w artykule [Set up Electronic invoicing](e-invoicing-set-up-overview.md).

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem procedur opisanych w tym artykule należy spełnić następujące wymagania wstępne:

- Osoba prawna musi być zarejestrowana jako podatnik w Polsce i musi posiadać ważny numer identyfikacji podatkowej (*Numer identyfikacji podatkowej*, lub NIP).
- Ważny certyfikat do podpisu cyfrowego musi być uzyskany od odpowiednich władz.
- Zapoznaj się z omówieniem fakturowania elektronicznego w sposób opisany [w temacie Fakturowanie elektroniczne](e-invoicing-service-overview.md).
- Zarejestruj się w RCS i skonfiguruj fakturowanie elektroniczne. Aby uzyskać więcej informacji, zobacz następujące artykuły:

    - [Zarejestruj się i zainstaluj usługę fakturowania elektronicznego](e-invoicing-sign-up-install.md)
    - [Ustawianie zasobów systemu Azure dla fakturowania elektronicznego](e-invoicing-set-up-azure-resources.md)
    - [Zainstaluj dodatek dla mikrousług w Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)

- Aktywuj integrację między aplikacją Finance lub Supply Chain Management a usługą fakturowania elektronicznego, jak opisano w punkcie [Aktywacja i konfiguracja integracji z usługą fakturowania elektronicznego](e-invoicing-activate-setup-integration.md).
- Utwórz certyfikaty i sekrety w Azure Key Vault i skonfiguruj Key Vault zgodnie z opisem w [Certyfikaty i sekrety klienta](e-invoicing-customer-certificates-secrets.md):

    - Tajny klucz numeru identyfikacji podatkowej firmy
    - Klucz tajny, który będzie zawierał klucz publiczny dostarczony przez polski narodowy system elektronicznego fakturowania ([KSeF](https://www.podatki.gov.pl/ksef))
    - Certyfikat do podpisywania cyfrowego

- Upewnij się, że zostały zaimportowane następujące konfiguracje formatu raportów elektronicznych (ER). Aby uzyskać więcej informacji, zobacz [Importowanie konfiguracji raportowania elektronicznego (RE)](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-import-ger-configurations.md).

    - Faktura sprzedaży (PL)
    - Faktura projektu (PL)
    - E-faktura zaliczkowa (PL)

## <a name="country-specific-configuration-for-the-polish-electronic-invoice-pl-feature"></a>Specyficzna dla kraju konfiguracja polskiej faktury elektronicznej (PL) Funkcja fakturowania elektronicznego

Niektóre parametry dostępne w funkcji **Polska faktura elektroniczna (PL)** są publikowane z wartościami domyślnymi. Przed wdrożeniem funkcji fakturowania elektronicznego w środowisku usługi przejrzyj wartości domyślne i zaktualizuj je zgodnie z wymaganiami, aby lepiej odzwierciedlały Twoją działalność biznesową.

1. Zaimportuj najnowszą wersję **Polskiej faktury elektronicznej (PL)** Funkcja globalizacji zgodnie z opisem w [Importuj funkcje z globalnego repozytorium](e-invoicing-import-feature-global-repository.md).
2. Utwórz kopię zaimportowanych funkcji globalizacji i wybierz dla niego dostawcę konfiguracji, zgodnie z opisem w tece [Tworzenie funkcji globalizacji](e-invoicing-create-new-globalization-feature.md).
3. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
4. Na karcie **Ustawienia** w siatce wybierz pozycję **Prześlij partię**, a następnie wybierz pozycję **Edytuj**.
5. Na karcie **Potok przetwarzania**, w sekcji **Potok przetwarzania**, wybierz akcję **(Wersja zapoznawcza) KSeF wyślij partię do systemu e-faktur**.
6. W sekcji **Parametry** wybierz **identyfikator klienta**, a następnie wybierz nazwę tajnych danych utworzonych dla numeru identyfikacji podatkowej firmy.
7. Wybierz **Nazwa certyfikatu**, a następnie wybierz nazwę utworzonego przez siebie certyfikatu cyfrowego.
8. Wybierz **Klucz publiczny**, a następnie wybierz nazwę sekretu, który utworzyłeś dla klucza publicznego.
9. Wybierz **adres URL** usługi i upewnij się, że jest skonfigurowany prawidłowy adres URL. Aby uzyskać adresy URL do testów i produkcji, wejdź na stronę polskiego Krajowego systemu fakturowania elektronicznego ([KSeF](https://www.podatki.gov.pl/ksef)).
10. W sekcji **Potok przetwarzania** wybierz akcję **(Wersja zapoznawcza) KSeF Pobierz status partii z systemu e-faktur**.
11. W sekcji **Parametry** wybierz **Adres serwisu** i upewnij się, że skonfigurowano prawidłowy adres URL.
12. Wybierz przycisk **Zapisz** i zamknij stronę.
13. Na karcie **Ustawienia** w siatce wybierz pozycję **Wyślij fakturę klienta**, a następnie wybierz pozycję **Edytuj**.
14. Na zakładce **Zasady stosowania**, w polu **LegalEntityID**, upewnij się, że w kolumnie **Wartość** jest skonfigurowany prawidłowy kod osoby prawnej.
15. Wybierz **Zapisz** (jeśli wprowadziłeś jakieś zmiany) i zamknij stronę.
16. Powtórz kroki od 13 do 15 dla ustawień funkcji **Wyślij fakturę za projekt** i **Wyślij fakturę zaliczkową**.

## <a name="finance-configuration"></a>Konfiguracja finansowa

Niektóre dodatkowe parametry muszą być skonfigurowane bezpośrednio w programie Finance.

1. Upewnij się, że zostały zaimportowane specyficzne dla danego kraju konfiguracje ER, które są wymagane w Polsce. Aby uzyskać więcej informacji, zobacz [Konfiguracja parametrów fakturowania elektronicznego](e-invoicing-set-up-parameters.md).
2. Przejdź do **Administrowanie organizacją** \> **Konfiguracja** \> **Parametry dokumentu elektronicznego**.
3. W sekcji **Dokument elektroniczny** dodaj rekordy dla nazw tabel **Dziennik faktury klienta**, **Faktura projektu** i **Faktura zaliczkowa**.
4. Dla każdej nazwy tabeli ustaw pola **Kontekst dokumentu** i **Mapowanie modelu dokumentu elektronicznego** zgodnie z krokiem 1.
5. Dla nazwy tabeli **Dziennik faktur klienta** wybierz **Rodzaje odpowiedzi**.
6. Utwórz typ odpowiedzi o takiej samej nazwie, jaka została zdefiniowana dla zmiennej powiązanej typu **Do klienta** w odpowiednich ustawieniach funkcji w RCS. Wprowadź następujące wartości:

    - W polu **Stan przesyłania** wybierz **W trakcie**.
    - W polu **Mapowania modelu** wybierz opcję **Format importu danych odpowiedzi KSeF (PL)**.

7. Powtórz kroki od 5 do 6 dla ustawień funkcji **Faktura za projekt** i **Faktura zaliczkowa** - dokumenty elektroniczne.
8. W obszarze roboczym **Zarządzanie funkcjami** musi być włączona funkcja **Kanały eksportu dla integracji fakturowania elektronicznego**. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
9. W obszarze roboczym **Raportowanie elektroniczne**, na kafelku **Konfiguracje raportowania** wybierz konfigurację **Model kontekstowy faktury klienta**.
10. Wybierz **Utwórz konfigurację**, a następnie w rozwijanym oknie dialogowym wybierz opcję **Utwórz z nazwy: Model kontekstu faktury klienta, Microsoft**, aby utworzyć konfigurację pochodną.
11. Otwórz konfigurację pochodną do edycji w projektancie i wybierz **Mapuj model do źródła danych**.
12. Otwórz definicję **DataChannel** do edycji w konstruktorze. W drzewie **Źródła danych** rozwiń kontener **$Context\_Channel**.
13. W polu **Wartość** wybierz pozycję **Edytuj** i wprowadź nazwę kanału danych. Wartość jest nazwą kanału danych skonfigurowanego w sekcji **Kanał eksportu** dla funkcji **Wysyłanie partii** w RCS.
14. Zapisz zmiany i zakończ konfigurację pochodnej.
15. Przejdź do **Administrowanie organizacją** \> **Konfiguracja** \> **Parametry dokumentu elektronicznego**.
16. <a id="channel"></a>W zakładce **Kanały integracyjne** dodaj kanał o tej samej nazwie, która została użyta w kroku 13.
17. W kolumnie **Firma** wprowadź wymagany kod osoby prawnej. W kolumnie **Kontekst dokumentu** odwołaj się do konfiguracji pochodnej.
18. Zapisz zmiany i zamknij stronę.

## <a name="finance-business-data-configuration"></a>Konfiguracja danych biznesowych dotyczących finansów

### <a name="prerequisites"></a>Wymagania wstępne

Podstawowy adres firmy musi być w Polsce.

### <a name="configure-legal-entity-data"></a>Skonfiguruj dane osób prawnych

#### <a name="enter-a-legal-entitys-address"></a>Wpisz adres osoby prawnej

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Organizacje** \> **Firmy**.
2. Wybierz osobę prawną, a następnie na karcie **Adresy** dodaj ważny adres główny dla tej osoby prawnej.

> [!NOTE]
> Upewnij się, że zdefiniowane są następujące obowiązkowe elementy adresu: kod kraju/regionu, kod pocztowy, miasto i numer budynku.

#### <a name="enter-a-legal-entitys-tax-registration-number"></a>Wpisz numer rejestracji podatkowej osoby prawnej

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Organizacje** \> **Firmy**.
2. Wybierz osobę prawną, a następnie na skróconej karcie **Rejestracja podatkowa** w polu **Numer identyfikacji podatkowej** wprowadź ważny numer identyfikacji podatkowej osoby prawnej. Numer ten będzie wykorzystywany jako numer identyfikacji podatkowej (NIP) sprzedawcy.

### <a name="configure-customer-data"></a>Skonfiguruj dane klienta

#### <a name="enter-a-customers-address"></a>Wprowadź adres klienta

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. Wybierz klienta, a następnie w zakładce **Adresy** dodaj prawidłowy adres dla klienta.

> [!NOTE]
> W przypadku adresów w Polsce upewnij się, że zdefiniowane są następujące elementy obowiązkowe: kod kraju/województwa, kod pocztowy, miasto i numer budynku. W przypadku adresów zagranicznych upewnij się, że zdefiniowane są przynajmniej następujące elementy obowiązkowe: kod kraju/regionu i miasto.

#### <a name="enter-a-customers-tax-registration-number"></a>Wprowadź numer rejestracji podatkowej klienta

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. Wybierz klienta, a następnie w zakładce **Faktura i dostawa** w polu **Numer zwolnienia podatkowego** wprowadź ważny numer rejestracji podatkowej klienta. Numer ten będzie wykorzystywany jako numer identyfikacji podatkowej (NIP) kupującego.

### <a name="configure-additional-data"></a>Skonfiguruj dane dodatkowe

Do faktur można dodać dowolne dodatkowe dane. Dane te zostaną umieszczone w specjalnej sekcji faktur elektronicznych o nazwie *DodatkowyOpis*.

#### <a name="configure-electronic-document-properties"></a>Skonfiguruj właściwości dokumentu elektronicznego

1. Przejdź do **Konta należności** \> **Ustawienia** \> **Typy właściwości dokumentów elektronicznych**.
2. Wybierz pozycję **Nowy**, aby dodać typ właściwości.
2. W polu **Typ** wprowadź wartość, która ma być użyta jako dodatkowy klucz danych (*Klucz*) w wynikowym pliku XML e-faktury.
3. Wybierz **Zastosowanie**, aby dodać odpowiednią tabelę.
4. Na stronie **Ustawienie stosowalności typu dokumentu elektronicznego** w polu **Nazwa tabeli** wybierz **Dziennik faktur klienta** i **Fakturę projektu**.
5. Dodaj tyle dodatkowych właściwości dokumentu, ile potrzebujesz.
6. Zapisz zmiany i wróć do strony **Typy właściwości dokumentów elektronicznych**.

    ![Typ właściwości dodany na stronie typów właściwości dokumentu elektronicznego.](media/e-invoicing-pol-parameters.jpg)

#### <a name="enter-additional-data"></a>Wprowadź dodatkowe dane

Wykonaj poniższe kroki, aby wprowadzić dodatkowe dane do faktury.

1. Przejdź do **Płatności** \> **Pytania i raporty** \> **Faktura** \> **Dziennik faktur**.
2. Zaznacz na liście fakturę, a następnie na pasku akcji, na karcie **Faktura**, w grupie **Właściwości** wybierz **Właściwości dokumentu elektronicznego**.
3. Wprowadź wymaganą wartość. Ta wartość zostanie użyta w polu *Wartosc* w wynikowym pliku XML e-faktury.

    ![Wartość wprowadzona na stronie właściwości dokumentu elektronicznego.](media/e-invoicing-pol-values.jpg)

> [!NOTE]
> Dodatkowe dane dla faktur projektowych możesz wprowadzić w podobny sposób w **Zarządzanie projektem i księgowość** \> **Faktury projektowe** \> **Faktura projektowa**.

## <a name="issue-electronic-invoices"></a>Wystawiaj faktury elektroniczne

Po wykonaniu wszystkich wymaganych kroków konfiguracyjnych możesz generować i przesyłać elektroniczne faktury za zaksięgowane faktury. Aby uzyskać więcej informacji na temat generowania faktur elektronicznych, zobacz [Wystawianie faktur elektronicznych w Finanse i Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md).

> [!NOTE]
> W celu przesłania polskiej faktury elektronicznej należy wykonać dodatkowe kroki oprócz standardowej procedury, która została opisana wcześniej.

W Polsce standardowa procedura składania dokumentów polega na generowaniu faktur elektronicznych i przechowywaniu ich po stronie serwisu. Nie przekazuje ich do KSeF. Aby przesłać faktury elektroniczne, wykonaj następujące kroki.

1. Przejdź do **Administrowanie organizacją** \> **Okresowe** \> **Dokumenty elektroniczne** \> **Uruchom proces składania wniosków w kanałach eksportowych**.
2. W polu **Kanał** wybierz kanał, który [wcześniej utworzyłeś](#channel). Następnie wybierz opcję **OK**.

Informacje o wynikach składania dokumentów można znaleźć w zakładce **Administracja organizacji** \> **Okresowa** \> **Dokumenty elektroniczne** \> **Dziennik składania dokumentów elektronicznych**).

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami](e-invoicing-get-started-service-administration.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
