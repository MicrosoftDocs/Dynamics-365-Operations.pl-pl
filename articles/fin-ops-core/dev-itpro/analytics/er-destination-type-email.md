---
title: Typ miejsca docelowego raportowania elektronicznego (ER)
description: Ten temat zawiera wyjaśnienia dotyczące konfigurowania miejsca docelowego poczty e-mail dla każdego składnika typu FOLDER lub PLIK w formacie raportowania elektronicznego (ER).
author: NickSelin
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: a575c04a5042e4db08f387bc7bce46225c109844
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753511"
---
# <a name="email-er-destination-type"></a>Typ miejsca docelowego raportowania elektronicznego (ER)

[!include [banner](../includes/banner.md)]

Po uruchomieniu formatu modułu Raportowanie elektroniczne (ER) można wygenerować jeden lub więcej dokumentów wychodzących. W formatach ER składniki formatu **Folder** lub **Plik** są używane do określania struktury dokumentów wychodzących. Istnieje możliwość skonfigurowania pocztowego miejsca docelowego dla tych typów składników w celu wysłania dokumentów wychodzących jako załączników wiadomości e-mail.

Pocztowe miejsce docelowe można skonfigurować dla każdego składnika **Folder** lub **Plik** formatu ER. W tym przypadku **każdy dokument wychodzący jest wysyłany pocztą e-mail osobno**. Na podstawie tego ustawienia lokalizacji docelowej wygenerowany dokument jest dostarczany jako załącznik wiadomości e-mail. 

> [!NOTE]
> Jeśli nie jest generowany żaden dokument, ponieważ dla odpowiedniego składnika **Plik** zostało skonfigurowane wyrażenie **Włączone**, które zwraca wartość logiczną **Fałsz**, nie jest wysyłana żadna wiadomość e-mail, nawet jeśli dla składnika skonfigurowano i włączono pocztowe miejsce docelowe.

Można również [zgrupować](#grouping) kilka składników **Folder** lub **Plik** razem, a następnie skonfigurować pocztowe miejsce docelowe dla wszystkich składników w grupie. W tym przypadku wszystkie dokumenty wychodzące generowane przez składniki należące do danej grupy **są wysyłane w postaci wielu załączników jednej wiadomości e-mail**. Na podstawie tego ustawienia lokalizacji docelowej każdy wygenerowany dokument jest dostarczany jako załącznik osobnej wiadomości e-mail.

> [!NOTE]
> Jeśli składnik **Plik** w grupie składników generuje co najmniej jeden dokument, jest wysyłana wiadomość e-mail. Jeśli składniki w grupie nie generują żadnego dokumentu, ponieważ dla każdego składnika **Plik** zostało skonfigurowane wyrażenie **Włączone**, które zwraca wartość logiczną **Fałsz**, nie jest wysyłana żadna wiadomość e-mail, nawet jeśli dla tej grupy składników skonfigurowano i włączono pocztowe miejsce docelowe.
>
> **E-mail** jest jedyną lokalizacją docelową, którą można skonfigurować dla grupy składników. Aby dostarczyć dokument wysyłany pocztą e-mail na podstawie ustawienia miejsca docelowego poczty e-mail dla grupy, dodaj jeszcze jeden rekord miejsca docelowego, zaznacz odpowiedni składnik, a następnie skonfiguruj inne miejsce docelowe dla tego rekordu.

Dla jednej konfiguracji formatu ER można skonfigurować wiele grup składników. W ten sposób można skonfigurować miejsce docelowe poczty e-mail dla każdej grupy składników i miejsca docelowego poczty e-mail dla każdego składnika.

## <a name="configure-an-email-destination"></a>Konfigurowanie pocztowego miejsca docelowego

Aby wysłać plik wyjściowy lub kilka plików wyjściowych pocztą elektroniczną, na stronie **Miejsce docelowe raportowania elektronicznego** na skróconej karcie **Miejsce docelowe — plik** zaznacz składnik lub grupę składników w siatce, a następnie wybierz opcję **Ustawienia**. W wyświetlonym oknie dialogowym **Ustawienia lokalizacji docelowej** na karcie **E-mail** w opcji **Włączone** zaznacz wartość **Tak**. Następnie możesz określić adresatów wiadomości e-mail oraz edytować jej temat i treść. Można zdefiniować stały tekst tematu i treści wiadomości e-mail lub używać [formuł](er-formula-language.md) ER w celu dynamicznego tworzenia tekstów wiadomości e-mail.

Adresy e-mail dla modułu ER można konfigurować na dwa sposoby. Konfigurację można wykonać w taki sam sposób, jak to robi funkcja zarządzania drukowaniem, lub też można rozpoznać adres e-mail za pomocą bezpośredniego odwołania do konfiguracji ER, korzystając z formuły.

[![Ustawianie opcji Włączone na Tak dla pocztowego miejsca docelowego](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>Typy adresów e-mail

Jeśli wybierzesz opcję **Edytuj** obok pola **Do** lub **DW** w oknie dialogowym **Ustawienia lokalizacji docelowej**, zostanie wyświetlone okno dialogowe **Wiadomość e-mail do**. Kliknij przycisk **Dodaj**, a następnie wybierz typ adresu e-mail, który ma być używany. Obecnie są obsługiwane dwa typy: **Adres e-mail zarządzania drukowaniem** i **Adres e-mail konfiguracji**.

[![Wybieranie typu adresu e-mail](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>Wiadomość e-mail zarządzania drukowaniem

Jeśli jako typ adresu e-mail wybierzesz opcję **Adres e-mail zarządzania drukowaniem**, można wprowadzić stałe adresy e-mail w oknie dialogowym **Wiadomość e-mail do**, ustawiając następujące pola:

- W polu **Źródło poczty e-mail** wybierz opcję **Brak**.
- W polu **Dodatkowe adresy e-mail, oddzielone średnikiem (;)** wprowadź stałe adresy e-mail.

Alternatywnie adresy e-mail można pozyskać z danych kontaktowych strony, dla której jest generowany dokument wychodzący. Aby używać adresów e-mail, które nie są stałe, w polu **Źródło poczty e-mail** zaznacz [rolę](../../fin-ops/organization-administration/overview-global-address-book.md#party-roles) strony dla plikowego miejsca docelowego. Obsługiwane są następujące role:

- Klient
- Dostawca
- Prospekt
- Kontakt
- Konkurent
- Pracownik
- Kandydat
- Potencjalny dostawca
- Niezatwierdzony dostawca

Na przykład aby skonfigurować pocztowe miejsce docelowe dla formatu ER, który będzie używany do przetwarzania płatności dla dostawców, wybierz rolę **Dostawca**.

Po wybraniu żądanej roli kliknij przycisk **Powiąż** (symbol łańcucha) obok pola **Konto źródłowe poczty e-mail**, aby otworzyć stronę [Projektant formuł](general-electronic-reporting-formula-designer.md). Następnie na tej stronie można skonfigurować formułę, która w czasie wykonywania zwraca numer konta strony przypisanej do skonfigurowanej roli z przetworzonego dokumentu do pocztowego miejsca docelowego.

> [!NOTE]
> Formuły są specyficzne dla konfiguracji ER.

Na stronie **Projektant formuł** w polu **Formuła** wprowadź specyficzne dla dokumentu odwołanie do obsługiwanej roli. Zamiast wpisywać odwołanie, w okienku **Źródło danych** znajdź i wybierz węzeł źródła danych reprezentujący konto skonfigurowanej roli, a następnie wybierz opcję **Dodaj źródło danych**, aby zaktualizować formułę. Na przykład jeśli skonfigurujesz pocztowe miejsce docelowe dla konfiguracji **Przelew bankowy ISO 20022**, która jest używana do przetwarzania płatności dla dostawców, węzłem reprezentującym konto dostawcy będzie `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

![Konfigurowanie konta źródłowego poczty e-mail](./media/er_destinations-emaildefineaddresssource.gif)

Jeśli numery kont skonfigurowanej roli są unikatowe w całym wystąpienia rozwiązania Microsoft Dynamics 365 Finance, pole **Firma źródła poczty e-mail** w oknie **Wiadomość e-mail do** może pozostać puste.

Alternatywnie może istnieć sytuacja, że różne strony w [globalnej książce adresowej](../../fin-ops/organization-administration/overview-global-address-book.md) zostały zarejestrowane w różnych firmach ([osobach prawnych](../../fin-ops/organization-administration/organizations-organizational-hierarchies.md#legal-entities)) w taki sposób, że wszystkie używają tego samego numeru konta do wypełniania skonfigurowanej roli. W takim przypadku numery kont skonfigurowanej roli nie są unikatowe w całym wystąpieniu rozwiązania Finance. Dlatego w celu jawnego wybrania strony nie można określić tylko numeru konta. Należy również określić firmę, w której zakresie strona została zarejestrowana do wypełniania skonfigurowanej roli. Kliknij przycisk **Powiąż** (symbol łańcucha) obok pola **Firma źródła poczty e-mail** w oknie dialogowym **Wiadomość e-mail do**, aby otworzyć stronę [aby otworzyć stronę](general-electronic-reporting-formula-designer.md). Następnie można skorzystać z tej strony, aby skonfigurować formułę zwracającą w czasie wykonywania kod firmy, w której zakresie musi się znajdować żądane źródło.

> [!TIP]
> Jeśli trzeba użyć kodu firmy do uruchomienia formatu ER, ale format ER nie udostępnia żadnego źródła danych, z którego można by uzyskać kod firmy, należy skonfigurować formułę `GetCurrentCompany()` za pomocą funkcji [GETCURRENTCOMPANY](er-functions-other-getcurrentcompany.md) wbudowanej w module ER.

> [!NOTE]
> Formuły są specyficzne dla konfiguracji ER.

Aby określić typ adresów e-mail, które muszą być używane w czasie wykonywania, w oknie dialogowym **Wiadomość e-mail do** wybierz opcję **Edytuj** obok pola **Do**, co spowoduje otwarcie rozwijanego okna dialogowego **Przypisz adresy e-mail**. Następnie ustaw wartości w następujących polach:

- W polu **Cel** wybierz żądane cele. Będą używane tylko adresy e-mail wybranych celów z kontaktów wykrytego podmiotu.
- W opcji **Kontakt podstawowy** ustaw wartość **Tak**, aby adresu e-mail skonfigurowanego dla wykrytego podmiotu używać jako podstawowego adresu e-mail.

> [!NOTE]
> Jeśli w polu **Cel** wybrano cele i równocześnie w opcji **Kontakt podstawowy** ustawiono wartość **Tak**, w czasie wykonywania będą używane wszystkie wiadomości e-mail spełniające co najmniej jedno skonfigurowane kryterium.

### <a name="configuration-email"></a>Adres e-mail konfiguracji

Wybierz opcję **Adres e-mail konfiguracji** jako typ adresu e-mail, jeśli używana konfiguracja ma w źródłach danych węzeł, który zwraca jeden adres e-mail lub wiele adresów e-mail oddzielonych średnikami (;). Za pomocą [źródeł danych](general-electronic-reporting.md#FormatComponentOutbound) i [funkcji](er-formula-language.md#functions) w projektancie formuł można uzyskać poprawnie sformatowany adres e-mail lub poprawnie sformatowane adresy e-mail, które są oddzielone średnikami. Jeśli na przykład zostanie użyta konfiguracja **Przelew bankowy ISO 20022**, węzłem reprezentującym podstawowy adres e-mail dostawcy pochodzący z danych kontaktowych dostawcy, pod który ma zostać wysłany list przewodni, będzie `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Konfigurowanie źródła adresu e-mail](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>Grupowanie składników formatu

Aby zgrupować składniki formatu, na stronie **Miejsce docelowe raportowania elektronicznego** na skróconej karcie **Miejsce docelowe — plik** zaznacz składniki w siatce, a następnie wybierz opcję **Grupuj**.

**E-mail** to jedyne wcześniej skonfigurowane miejsce docelowe, które jest nadal dostępne dla wybranych składników. Nie są dostępne żadne inne wcześniej skonfigurowane miejsca docelowe, ponieważ są one uważane za nieobsługiwane dla grupy składników. W razie potrzeby będziesz otrzymywać powiadomienia o tych zmianach.

Poprzednio dodany rekord jest traktowany jako nagłówek tworzonej grupy. Ten rekord nagłówka zawiera ustawienia pocztowego miejsca docelowego dla grupy. Inne rekordy są elementami członkowskimi grupy, które będą korzystały z ustawień pocztowego miejsca docelowego określonych w rekordzie nagłówka grupy.

Aby rozgrupować składniki formatu, na skróconej karcie **Miejsce docelowe — plik** wybierz rekord należący do grupy, a następnie wybierz opcję **Rozgrupuj**.

- W przypadku wybrania rekordu nagłówka zostanie rozgrupowane cała grupa.
- W przypadku wybrania rekordu elementu członkowskiego, który jest ostatnim rekordem elementu członkowskiego w grupie, zostanie rozgrupowana cała grupa.
- W przypadku wybrania rekordu elementu członkowskiego, który nie jest ostatnim rekordem elementu członkowskiego w grupie, rekord ten zostanie wykluczony z bieżącej grupy.

Na poniższej ilustracji przedstawiono strukturę formatu ER, który został skonfigurowany w celu utworzenia spakowanego pliku wychodzącego zawierającego tekst ponaglenia i odpowiednie faktury dla odbiorcy w formacie PDF.

[![Struktura formatu modułu ER powodującego generowanie dokumentów wychodzących](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

Na poniższej ilustracji przedstawiono proces grupowania poszczególnych składników i włączania miejsca docelowego **E-mail** dla nowej grupy w sposób opisany w tym temacie, tak aby tekst ponaglenia był wysyłany wraz z odpowiednimi fakturami dla odbiorcy jako załączniki wiadomości e-mail.

[![Grupowanie poszczególnych składników i włączanie pocztowego miejsca docelowego](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- [Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)
- [Projektant formuł w module Raportowanie elektroniczne (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]