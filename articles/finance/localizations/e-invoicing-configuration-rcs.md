---
title: Konfigurowanie fakturowania elektronicznego w usługach Regulatory Configuration Services (RCS)
description: W tym temacie wyjaśniono, jak skonfigurować Fakturowanie elektroniczne w Dynamics 365 Regulatory Configuration Services (RCS).
author: gionoder
ms.date: 07/29/2021
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
ms.openlocfilehash: 98ba40da7b365e46e1c624ba70c7dc048144e2c7137e8fd8eb5abe348028ce35
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757981"
---
# <a name="configure-electronic-invoicing-in-regulatory-configuration-services-rcs"></a>Konfigurowanie fakturowania elektronicznego w usługach Regulatory Configuration Services (RCS)

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o możliwościach konfiguracyjnych Fakturowanie elektroniczne w Dynamics 365 Regulatory Configuration Services (RCS).

To dzięki możliwościom konfiguracji funkcji Fakturowanie elektroniczne pomaga spełnić wymagania biznesowe i regulacyjne dotyczące faktur elektronicznych bez konieczności kodowania. A w scenariuszach, w których tekstury elektroniczne muszą być elektronicznie zatwierdzane przez usługi sieciowe, opcje konfiguracyjne również spełnić wymagania dotyczące wymiany wiadomości z usługami sieciowymi bez wykonania kodu.

## <a name="electronic-reporting"></a>Raportowanie elektroniczne

Raportowanie elektroniczne (ER) obsługuje Fakturowanie elektroniczne.

Mapowanie i formaty modelu danych to konfigurowalne komponenty, które są tworzone i obsługiwane za pośrednictwem ER i używane w Fakturowanie elektroniczne. Projektant formatu ER to narzędzie do tworzenia i obsługi formatów plików. Służy do konfigurowania funkcji fakturowania elektronicznego.

Aby uzyskać więcej informacji, zobacz [Omówienie raportowania elektronicznego (RE)](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

## <a name="electronic-invoicing-features"></a>Funkcje fakturowania elektronicznego

Funkcje fakturowania elektronicznego są odpowiedzialne za generowanie faktur elektronicznych za pośrednictwem funkcji Fakturowanie elektroniczne. Hermetyzują reguły konfiguracji i używają ich do przetwarzania danych, które Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management wysyłają do funkcji Fakturowanie elektroniczne i do faktur elektronicznych.

Funkcje obsługują również scenariusze, w których wymagana jest zgodność ze specyfikacjami formatu pliku, a wynikiem jest samodzielny plik elektroniczny. W większości przypadków specyfikacje formatu pliku są publikowane przez organ podatkowy.

Wreszcie, funkcje obsługują wymianę wiadomości z zewnętrznymi usługami sieciowymi, które są hostowane przez organ podatkowy lub przez jakąś akredytowaną stronę, oraz prośby o autoryzację lub pieczęć zatwierdzenia na fakturze elektronicznej.

## <a name="availability-of-electronic-invoicing-features"></a>Dostępność funkcji fakturowania elektronicznego

Dostępność funkcji fakturowania elektronicznego zależy od kraju lub regionu. Chociaż niektóre funkcje są ogólnie dostępne, inne są w wersji zapoznawczej.

### <a name="generally-available-features"></a>Ogólnie dostępne funkcje

W poniższej tabeli przedstawiono funkcje fakturowania elektronicznego, które są obecnie dostępne ogólnie.

| Kraj/region | Nazwa funkcji                         | Dokument biznesowy |
|----------------|--------------------------------------|-------------------|
| Austria        | Faktury elektroniczne w Austrii (AT)    | Faktury sprzedaży i faktury za projekty |
| Belgia        | Faktura elektroniczna w Belgii (BE)      | Faktury sprzedaży i faktury za projekty |
| Brazylia         | Brazylijski NF-e (BR)                  | Dokument fiskalny modelu 55, listy korekty, anulowania i odrzucenia |
| Brazylia         | Brazylijski NFS-e ABRASF Curitiba (BR) | Obsługa dokumentów fiskalnych |
| Brazylia         | Import brazylijskiego NF-e z poczty e-mail (BR) | Dokument fiskalny modelu 55 |
| Dania        | Duńska faktura elektroniczna (DK)       | Faktury sprzedaży i faktury za projekty |
| Egipt          | Egipska faktura elektroniczna (EG)     | Faktury sprzedaży i faktury za projekty |
| Estonia        | Estońska faktura elektroniczna (EE)     | Faktury sprzedaży i faktury za projekty |
| Finlandia        | Fińska faktura elektroniczna (FI)      | Faktury sprzedaży i faktury za projekty |
| Francja         | Francuska faktura elektroniczna (FR)       | Faktury sprzedaży i faktury za projekty |
| Niemcy        | Niemiecka faktura elektroniczna (DE)       | Faktury sprzedaży i faktury za projekty |
| Włochy          | FatturaPA (IT)                       | Faktury sprzedaży i faktury za projekty |
| Holandia    | Holenderska faktura elektroniczna (NL)        | Faktury sprzedaży i faktury za projekty |
| Norwegia         | Norweska faktura elektroniczna (NIE)    | Faktury sprzedaży i faktury za projekty |
| Hiszpania          | Hiszpańska faktura elektroniczna (ES)      | Faktury sprzedaży i faktury za projekty |
| Europa         | Faktura elektroniczna PEPPOL            | Faktury sprzedaży PEPPOL i faktury za projekty |
| Europa         | Faktura sprzedawcy PEPPOL                | PEPPOL import faktur dostawców |

### <a name="preview-features"></a>Funkcje w wersji zapoznawczej

W poniższej tabeli przedstawiono funkcje fakturowania elektronicznego, które są obecnie dostępne w wersji zapoznawczej.

| Kraj/region | Nazwa funkcji                         | Dokument biznesowy |
|----------------|--------------------------------------|-------------------|
| Meksyk         | Meksykański CFDI (MX)                    | Faktury sprzedaży, dokumenty dostawy, przesunięcia magazynowe, uzupełnienia płatności i anulacje |

### <a name="configurable-components-of-electronic-invoicing-features"></a>Konfigurowalne składniki funkcji fakturowania elektronicznego

Funkcje fakturowania elektronicznego obejmują następujące grupy konfigurowalnych składników:

- **Formaty**: pozwalają skonfigurować, co musi generować Fakturowanie elektroniczne, gdy dokument elektroniczny staje się fakturą elektroniczną. Formaty obejmują konfigurację formatu faktury elektronicznej oraz plików i wiadomości używanych do przesyłania żądań i otrzymywania odpowiedzi, gdy wymagana jest komunikacja z zewnętrzną usługą sieciową.
- **Akcje**: Akcje umożliwiają skonfigurowanie sposobu, w jaki Fakturowanie elektroniczne generuje przekształcenie dokumentu elektronicznego przesłanego przez rozwiązanie Finance and Supply Chain Management w fakturę elektroniczną.
- **Reguły stosowania**: Reguły stosowania pozwalają skonfigurować kontekst, który musi uwzględniać Fakturowanie elektroniczne, aby przetwarzać funkcję fakturowania elektronicznego.
- **Zmienne**: zmienne umożliwiają skonfigurowanie obsługi logiki konfiguracji. Zmienne mogą być wartościami wejściowymi do wykonywania określonej akcji. Alternatywnie mogą służyć jako wymiana wartości między rozwiązaniami Finance and Supply Chain Management a funkcją fakturowania elektronicznego.
- **Mapowanie modelu dokumentu elektronicznego**: Odwzorowanie modelu dokumentu elektronicznego umożliwia skonfigurowanie mapowania modelu ER. Mapowanie modelu definiuje mapowanie danych faktury abstrakcyjnej, która jest zintegrowana z funkcją Fakturowanie elektroniczne podczas przesyłania dokumentów elektronicznych.
- **Model kontekstu faktury**: Model kontekstu faktury umożliwia skonfigurowanie modelu kontekstu faktury ER i zdefiniowanie kontekstu funkcji fakturowania elektronicznego.
- **Typy odpowiedzi**: Typy odpowiedzi umożliwiają skonfigurowanie, co Fakturowanie elektroniczne musi aktualizować w rozwiązaniu Finance and Supply Chain Management w wyniku przetwarzania faktury elektronicznej.

### <a name="formats"></a>Formaty

Na poniższych listach przedstawiono konfiguracje formatów elektronicznego fakturowania, które są dostępne dla funkcji fakturowania elektronicznego.

#### <a name="austrian-at-electronic-invoices-sales-and-project-invoices-for-austria"></a>Austriackie faktury elektroniczne (AT): faktury sprzedaży i faktury za projekty dla Austrii

- Faktura sprzedaży OIOUBL
- Faktura za projekt OIOUBL
- OIOUBL Faktura korygująca za sprzedaż
- Faktura korygująca za projekt OIOUBL

#### <a name="belgian-be-electronic-invoice-sales-and-project-invoices-for-belgium"></a>Belgijska faktura elektroniczna (BE): Faktury sprzedaży i projektu dla Belgii

- Faktura sprzedaży UBL BE
- Faktura projektu UBL BE
- Faktura korygująca za projekt UBL BE
- Faktura korygująca sprzedaż UBL BE

#### <a name="brazilian-br-nf-e-nf-e-federal-brazil"></a>Brazylijski (BR) NF-e: Federalne NF-e (Brazylia)

- Przesyłanie NF-e format eksportu (BR)
- Format eksportu listu korygującego NF-e (BR)
- Anulowanie NF-e format eksportu (BR)
- Odrzucanie NF-e format eksportu (BR)

#### <a name="brazilian-nfs-e-br-nfs-e-abrasf-curitiba-city"></a>Brazylijskie NFS-e (BR): NFS-e ABRASF miasto Curitiba

- NFS-e ABRASF Curitiba (BR)
- Zapytanie o NFS-e ABRASF Curitiba (BR)

#### <a name="danish-dk-electronic-invoice-sales-and-project-invoices-for-denmark"></a>Duńska (DK) faktura elektroniczna: faktury sprzedaży i faktury za projekty dla Danii

- Faktura sprzedaży OIOUBL
- Faktura za projekt OIOUBL
- OIOUBL Faktura korygująca za sprzedaż
- Faktura korygująca za projekt OIOUBL

#### <a name="dutch-nl-electronic-invoice-sales-and-project-invoices-for-netherlands"></a>Holenderska faktura elektroniczna (NL): Faktury sprzedaży i projektu dla Holandii

- Faktura sprzedaży UBL NL
- Faktura projektu UBL NL
- Faktura korygująca za projekt UBL NL
- Faktura korygująca sprzedaż UBL NL

#### <a name="egyptian-eg-electronic-invoice-sales-and-project-invoices-for-egypt"></a>Egipska faktura elektroniczna (EG): faktury sprzedaży i projektów dla Egiptu

- Faktura sprzedaży (EG) (fakturowanie)
- Faktura projektu (EG) (fakturowanie)

#### <a name="estonian-ee-electronic-invoice-sales-and-project-invoices-for-estonia"></a>Estońska faktura elektroniczna (EE): Faktury sprzedaży i projektu dla Estonii

- Faktura sprzedaży (EE)
- Faktura projektu (EE)

#### <a name="finnish-fi-electronic-invoice-sales-and-project-invoices-for-finland"></a>Fińska faktura elektroniczna (FI): Faktury sprzedaży i projektu dla Finlandii

- Faktura sprzedaży (FI)
- Faktura projektu (FI)

#### <a name="french-fr-electronic-invoice-sales-and-project-invoices-for-france"></a>Faktura elektroniczna we Francji (FR): Faktury sprzedaży i projektu dla Francji

- Faktura sprzedaży UBL FR
- Faktura projektu UBL FR
- Faktura korygująca za projekt UBL FR
- Faktura korygująca sprzedaż UBL FR

#### <a name="german-de-electronic-invoice-sales-and-project-invoices-for-germany"></a>Niemiecka faktura elektroniczna (DE): Faktury sprzedaży i projektu dla Niemiec

- Faktura sprzedaży (DE)
- Faktura projektu (DE)

#### <a name="italian-it-electronic-invoice-sales-and-project-invoices-for-italy"></a>Włoska faktura elektroniczna (IT): faktury sprzedaży i projektu dla Włoch

- Faktura sprzedaży (IT)
- Faktura projektu (IT)

#### <a name="mexican-mx-cfdi-cfdi-for-mexico"></a>CFDI meksykański (MX) : CFDI dla Meksyku

- Format faktury CFDI (MX)
- Dokument dostawy CFDI (MX)
- Przeniesienia zapasów CFDI (MX)
- Format płatności CFDI (MX)
- Format anulowania faktury CFDI (MX)

#### <a name="norwegian-no-electronic-invoice-sales-and-project-invoices-for-norway"></a>Norweska faktura elektroniczna (NO): Faktury sprzedaży i projektu dla Norwegii

- Faktura sprzedaży OIOUBL
- Faktura za projekt OIOUBL
- OIOUBL Faktura korygująca za sprzedaż
- Faktura korygująca za projekt OIOUBL

#### <a name="peppol-electronic-invoice-peppol-sales-and-project-invoices"></a>Faktura elektroniczna PEPPOL: faktury sprzedaży i faktury projektowe PEPPOL

- Faktura sprzedaży PEPPOL
- Faktura za projekt PEPPOL
- PEPPOL Faktura korygująca za sprzedaż
- Faktura korygująca za projekt PEPPOL

#### <a name="spanish-es-electronic-invoice-sales-and-project-invoices-for-spain"></a>Hiszpańska faktura elektroniczna (ES): Faktury sprzedaży i projektu dla Hiszpanii

- Faktura sprzedaży (ES)
- Faktura projektu (ES)

Poza konfiguracjami formatu ER, które są dostępne do natychmiastowego użycia z usługą Elektronicznego Fakturowania, można również tworzyć własne konfiguracje formatu ER. Jednak konfiguracje formatu, które są tworzone do użycia z funkcjami Elektronicznego Fakturowania nie obsługują bezpośredniego odniesienia do tabel Finance lub Supply Chain Management ani żadnych odpowiadających im metadanych. Obsługiwane są tylko odwołania do mapowania modelu ER.

### <a name="actions"></a>Akcje

W poniższej tabeli wymieniono dostępne akcje oraz informacje o tym, czy są one obecnie ogólnie dostępne, czy nadal w podglądzie.

| Akcja                                        | opis                                                                  | Dostępność         |
|-----------------------------------------------|------------------------------------------------------------------------------|----------------------|
| Przekształcanie dokumentu                            | Uruchom format raportowania elektronicznego, aby przekształcić dokument.                   | Ogólnie dostępne  |
| Podpisz dokument XML                             | Podpisz dokumenty XML podpisem cyfrowym.                                   | Ogólnie dostępne  |
| Podpisz dokument json dla egipskiego urzędu skarbowego | Podpisuj dokumenty JSON podpisem cyfrowym dla egipskiego urzędu skarbowego.       | Ogólnie dostępne  |
| Zintegruj się z egipską usługą ETA           | Skontaktuj się z egipskim organem podatkowym.                                     | Ogólnie dostępne  |
| Wywołaj usługę brazylijską SEFAZ                  | Zintegruj z brazylijską usługą SEFAZ do przesyłania dokumentów fiskalnych.       | Ogólnie dostępne  |
| Wywołaj usługę meksykańskiego certyfikatu PAC                      | Integracja z meksykańską usługą PAC w celu przesyłania CFDI.                      | Wersja próbna           |
| Przetwarzanie odpowiedzi                              | Przeanalizuj odpowiedź otrzymaną z wywołania usługi sieci web.                     | Ogólnie dostępne  |
| Użyj MS Power Automate                         | Integruj z przepływem zbudowanym w Microsoft Power Automate.                       | Wersja próbna           |

### <a name="applicability-rules"></a>Reguły zastosowania

Reguły stosowania to konfigurowalne klauzule, które są zdefiniowane na poziomie funkcji fakturowania elektronicznego. Reguły są skonfigurowane tak, aby zapewnić kontekst do wykonywania funkcji fakturowania elektronicznego za pośrednictwem zestawu funkcji fakturowania elektronicznego.

Gdy dokument biznesowy z Finance lub Supply Chain Management jest przesyłany do fakturowania elektronicznego, dokument biznesowy nie zawiera wyraźnego odniesienia, które umożliwia ustawieniu funkcji fakturowania elektronicznego wywołanie określonej funkcji fakturowania elektronicznego w celu przetworzenia zgłoszenia.

Niemniej jednak, odpowiednio skonfigurowany, dokument biznesowy zawiera niezbędne elementy, które umożliwiają fakturowanie elektroniczne w celu ustalenia, którą funkcję fakturowania elektronicznego należy wybrać, a następnie wygenerowania faktury elektronicznej.

Reguły stosowania umożliwiają zestawowi fakturowania elektronicznego znalezienie dokładnych funkcji fakturowania elektronicznego, których należy użyć do przetworzenia przedłożenia. Odbywa się to poprzez dopasowanie treści z przesłanego dokumentu biznesowego do klauzul z Reguł stosowalności.

Na przykład dwie funkcje fakturowania elektronicznego z powiązanymi regułami stosowalności są wdrażane w zestawie możliwości fakturowania elektronicznego.

| Funkcja fakturowania elektronicznego | Reguły zastosowania        |
|------------------------------|--------------------------- |
| A                            | <p>Kraj = BR</p><p>i</p><p>Osoba prawna = BRMF</p>  |
| mld                            | <p>Kraj = MX</p><p>i</p><p>Osoba prawna = MXMF</p>  |

Jeśli dokument biznesowy z Finance lub Supply Chain Management zostanie przesłany do zestawu funkcji Fakturowanie elektroniczne, dokument biznesowy zawiera następujące atrybuty wypełnione jako:

- Kraj = BR
- Osoba prawna = BRMF

W zestawie możliwości fakturowania elektronicznego jest wybierana funkcja fakturowania elektronicznego **A**, która umożliwia przetwarzanie przesyłania i generowanie faktury elektronicznej.

Podobnie, jeśli dokument biznesowy zawiera:

- Kraj = MX
- Osoba prawna = MXMF

W celu wygenerowania faktury elektronicznej wybrano funkcję fakturowania elektronicznego **B**.

Konfiguracja reguł możliwości zastosowania nie może być niejednoznaczna. Oznacza to, że dwie lub więcej funkcji fakturowania elektronicznego nie może mieć tych samych klauzul, w przeciwnym razie nie doprowadzi to do braku wyboru. W przypadku duplikowania funkcji fakturowania elektronicznego, aby uniknąć niejednoznaczności, należy zastosować dodatkowe klauzule, aby umożliwić ustawieniu funkcji fakturowania elektronicznego rozróżnienie między tymi dwoma funkcjami fakturowania elektronicznego.

Rozważmy na przykład funkcję fakturowania elektronicznego **C**. Ta funkcja jest kopią funkcji fakturowania elektronicznego **A**.

| Funkcja fakturowania elektronicznego | Reguły zastosowania        |
|------------------------------|--------------------------- |
| A                            | <p>Kraj = BR</p><p>i</p><p>Osoba prawna = BRMF</p>  |
| C                            | <p>Kraj = BR</p><p>i</p><p>Osoba prawna = BRMF</p>  |

W tym przykładzie funkcja **C** jest przed przesłaniem dokumentu biznesowego, który zawiera następujące elementy:

- Kraj = BR
- Osoba prawna = BRMF

Funkcja fakturowania elektronicznego nie jest w stanie rozróżnić, która funkcja fakturowania elektronicznego musi zostać użyta do przetworzenia zgłoszenia, ponieważ zgłoszenia zawierają dokładnie te same klauzule.

Aby dokonać rozróżnienia między tymi dwiema funkcjami za pomocą reguł stosowania, należy dodać nową klauzulę do jednej z funkcji, aby umożliwić ustawieniu fakturowania elektronicznego wybranie odpowiedniej funkcji fakturowania elektronicznego.

| Funkcja fakturowania elektronicznego | Reguły zastosowania        |
|------------------------------|--------------------------- |
| A                            | <p>Kraj = BR</p><p>i</p><p>Osoba prawna = BRMF</p>  |
| C                            | <p>Kraj = BR</p><p>i</p><p>Osoba prawna = BRMF</p><p>i</p><p>Model=55</p>  |

Do obsługi tworzenia bardziej złożonych klauzul są dostępne następujące zasoby:

Operatory logiki:
- i
- lub

Typy operatorów:
- Equal
- Not equal
- Greater than
- Less than
- Większe lub równe
- Mniejsze lub równe
- Contains
- Zaczyna się od

Typy danych:
- Ciąg
- Identyfikator
- Wartość logiczna
- Data
- UUID

Możliwość grupowania i rozgrupowania klauzul.
Przykład wygląda następująco.

| Funkcja fakturowania elektronicznego | Reguły zastosowania        |
|------------------------------|--------------------------- |
| C                            | <p>Kraj = BR</p><p>i</p><p>( Osoba prawna = BRMF</p><p>lub</p><p>Model=55)</p>  |


## <a name="configuration-providers"></a>Dostawcy konfiguracji

Dostawcy konfiguracji zapewniają funkcje fakturowania elektronicznego i ich składniki ER, takie jak mapowanie modelu, konfiguracja formatu i model kontekstu. Publikują funkcje fakturowania elektronicznego i komponenty ER w powiązanym repozytorium globalnym. Wtedy mogą je pobrać inne organizacje.

Przed skonfigurowaniem funkcji fakturowania elektronicznego za pomocą funkcji RCS należy skonfigurować swoją organizację jako dostawcę konfiguracji w module **Raportowanie elektroniczne**. Aby uzyskać informacje o tym, jak ustawić konfigurację dostawcy jako **Aktywny**, zobacz [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="viewing-electronic-invoicing-features-in-the-global-repository"></a>Przeglądanie funkcji fakturowania elektronicznego w repozytorium globalnym

Aby przeglądać funkcje fakturowania elektronicznego, które są dostępne w repozytorium globalnym dla określonego dostawcy konfiguracji, zsynchronizuj wystąpienie RCS swojej organizacji. Po zakończeniu synchronizacji lista dostępnych funkcji fakturowania elektronicznego jest aktualizowana.

## <a name="importing-electronic-invoicing-features"></a>Importowanie funkcji fakturowania elektronicznego

Przed użyciem lub skonfigurowaniem funkcji fakturowania elektronicznego należy zaimportować je do instancji RCS organizacji. Operacja importu tworzy lokalną kopię funkcji i kopiuje wszystkie artefakty ER używane przez funkcje (na przykład konfiguracje formatu i konfiguracje modeli) do instancji RCS organizacji.

Możesz zaimportować funkcje fakturowania elektronicznego od dowolnego dostawcy konfiguracji.

## <a name="creating-electronic-invoicing-features"></a>Tworzenie funkcji fakturowania elektronicznego

Możesz utworzyć funkcję fakturowania elektronicznego od podstaw lub możesz ją wyprowadzić z innej funkcji fakturowania elektronicznego.

Podczas tworzenia od podstaw funkcji fakturowania elektronicznego należy ręcznie dodać składniki ER (na przykład konfiguracje wersji funkcji i inne konfiguracje, takie jak konfiguracja wersji funkcji i konfiguracja aplikacji). Po utworzeniu funkcji na podstawie innej funkcji nowa funkcja dziedziczy wszystkie konfiguracje z oryginału. 

## <a name="electronic-invoicing-feature-version"></a>Wersja funkcji fakturowania elektronicznego

Funkcje fakturowania elektronicznego są wersjonowane. Po utworzeniu nowej wersji numer wersji jest automatycznie zwiększany. Dla nowej wersji można zdefiniować datę „od dnia wejścia w życie”.

Wersje funkcji fakturowania elektronicznego mają cykl życia, który ma maksymalnie trzy statusy:

- **Wersja robocza** — jeśli wersja funkcji ma ten stan, można edytować jej atrybuty konfiguracji oraz dowolne artefakty (na przykład konfiguracje formatów plików).
- **Ukończono** — jeśli wersja funkcji ma ten stan, została opublikowana w repozytorium globalnym skojarzonym z organizacją. Nie można już edytować wersji funkcji ani składników funkcji ER.
- **Opublikowano** — jeśli wersja funkcji ma ten stan, została opublikowana w funkcji Fakturowanie elektroniczne. Nie można już edytować wersji funkcji ani składników funkcji ER.

### <a name="feature-configurations"></a>Konfiguracje funkcji

Konfiguracje funkcji zawierają wszystkie konfiguracje formatu ER używane przez funkcje fakturowania elektronicznego. Wszystkie pliki elektroniczne używane przez funkcję fakturowania elektronicznego podczas przetwarzania pochodzą z konfiguracji formatu, które zostały dodane do konfiguracji funkcji tej funkcji.

Z konfiguracji funkcji można uzyskać dostęp do konstruktora formatów ER, który jest narzędziem ER używanym do tworzenia konfiguracji formatów.

### <a name="feature-setup"></a>Konfiguracja funkcji

Ustawienia funkcji są używane w połączeniu z konfiguracjami funkcji. Każda konfiguracja funkcji zawiera zestaw akcji, reguł zastosowania i zmiennych, które zapewniają oczekiwane zachowanie, dzięki czemu funkcja fakturowania elektronicznego może spełniać określone wymagania faktury elektronicznej.

### <a name="application-setup"></a>Konfiguracja aplikacji

Ustawienia aplikacji muszą być skojarzone z wcześniej utworzoną połączoną aplikacją.

Za pomocą konfiguracji aplikacji można skonfigurować część funkcji fakturowania elektronicznego, którą należy wykonać w rozwiązaniu Finance i Supply Chain Management. Co najmniej trzy konfigurowalne komponenty są obowiązkowe, niezależnie od funkcji fakturowania elektronicznego:

- **Nazwa tabeli** — jednostka w Finance i Supply Chain Management, która zawiera zaksięgowane faktury i na których opiera się funkcja fakturowania elektronicznego.
- **Kontekst** — nazwa modelu kontekstu faktury, który został skonfigurowany za pomocą ER.
- **Mapowanie dokumentów biznesowych** — nazwa modelu mapowania faktury, który został skonfigurowany za pomocą ER.

> [!IMPORTANT]
> Konfigurację wprowadzoną w konfiguracji aplikacji można wyświetlić w programie Finance i Supply Chain Management. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametr dokumentu elektronicznego**. Na karcie **Dokument elektroniczny** wybierz pozycję **Wdrażaj**, a następnie wybierz opcję **Połączona aplikacja**.

### <a name="deploying-feature-versions"></a>Wdrażanie wersji funkcji

W RCS można użyć polecenia **Wdrożenie**, aby opublikować wersję funkcji fakturowania elektronicznego. Wybierz opcję **Rozmieszczaj**, a następnie wybierz jedną z następujących opcji w celu zdefiniowania celu wdrożenia: 

- **Środowisko usługi** — jeśli celem wdrożenia jest środowisko usługi, wersja funkcji fakturowania elektronicznego jest opublikowana w środowisku usług. Fakturowanie elektroniczne jest wtedy gotowy do odbierania i przetwarzania dokumentów elektronicznych wysyłanych przez Finance i Supply Chain Management.
- **Połączona aplikacja** — Jeśli celem wdrożenia jest połączona aplikacja, konfiguracja dostarczona przez instalację aplikacji jest zapisywana w instancji Finance i Supply Chain Management, która była wcześniej z nią skojarzona.

Tylko wersje funkcji fakturowania elektronicznego, które mają stan **Zakończono**, mogą być wdrażane w środowisku usług lub połączonej aplikacji.

### <a name="removing-feature-versions"></a>Usuwanie wersji funkcji

W RCS za pomocą polecenia **Cofnij wdrożenie** można usunąć określoną wersję funkcji fakturowania elektronicznego ze środowiska usługowego w funkcji Fakturowanie elektroniczne.

> [!IMPORTANT]
> Polecenie **Cofnij wdrożenie** działa tylko w środowiskach usług. Nie usuwa wersji funkcji fakturowania elektronicznego z połączonych aplikacji.

### <a name="rebasing-electronic-invoicing-features"></a>Zmiana bazy funkcji fakturowania elektronicznego

Gdy jedna funkcja fakturowania elektronicznego jest pochodną innej, polecenie **Zmiana bazy** aktualizuje tę funkcję za pomocą zmian wprowadzonych w pierwotnej funkcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Wystawiaj faktury elektroniczne w Finance i Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
