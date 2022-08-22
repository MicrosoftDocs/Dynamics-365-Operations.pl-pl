---
title: Obsługa parametrów wywołań modeli danych ER
description: W tym artykule opisano sposób implementacji parametrów wywołań modeli danych raportowania elektronicznego (ER).
author: kfend
ms.date: 03/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.custom: ''
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula, ERDataModelDesigner
ms.openlocfilehash: 5be189c19d963991ec012de189bbf7b721b88fef
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275997"
---
# <a name="support-parameterized-calls-of-er-data-models"></a>Obsługa parametrów wywołań modeli danych ER

[!include [banner](../includes/banner.md)]

Aby wygenerować dokumenty biznesowe, należy skonfigurować rozwiązanie [raportowania elektronicznego](general-electronic-reporting.md) zawierające następujące składniki raportowania elektronicznego:

- **[Format](er-overview-components.md#format-component)** — ten składnik określa strukturę dokumentu biznesowego.
- **Mapowanie formatu** — ten składnik steruje możliwością wypełnienia dokumentu biznesowego w czasie wykonywania.
- **[Mapowanie modelu](er-overview-components.md#model-mapping-component)** — ten składnik określa, jakie dane są ściągane z aplikacji do mapowania formatu.
- **[Model danych](er-overview-components.md#data-model-component)** – Ten składnik przechodzi informacje między poszczególnymi składnikami.

Po uruchomieniu formatu ER każdy element formatu jest uruchamiany, począwszy od elementu głównego formatu. Za każdym razem, gdy uruchamiany element formatu zawiera powiązanie ze [źródłem danych](general-electronic-reporting.md#configuring-data-model-mappings-for-outgoing-documents), źródło danych jest uruchamiane w celu dostarczenia oczekiwanego dane i użyj ich do wypełnienia elementu formatu. Gdy zostanie wywołane źródło danych typu *Model*, zostanie wywołane odpowiednie mapowanie modelu, które będzie ciągnięte z aplikacji zgodnie z ustawieniami mapowania modelu.

Wcześniej tych wywołań mapowania modelu nie można było sparametryzować, aby były zależne od logiki uruchamianego formatu. Obsługiwany był tylko następujący przepływ danych.

<table>
<tbody>
<tr align="center">
<td>
<b>Format</b><br>
Element&nbsp;formatu<br>
&nbsp;
</td>
<td>
<i>Powiązanie</i><br>
&gt;&nbsp;żądanie&nbsp;&gt;<br>
&lt;&nbsp;wartość&nbsp;&lt;
</td>
<td><b>mapowanie&nbsp;formatu</b><br>
Źródło danych<br>
&nbsp;
</td>
<td>
<i>Model&nbsp;danych</i><br>
&gt;&nbsp;żądanie&nbsp;&gt;<br>
&lt;&nbsp;wartość&nbsp;&lt;
</td>
<td>
<b>Mapowanie&nbsp;modelu</b><br>
Źródło&nbsp;danych<br>
&nbsp;
</td>
<td>
<i>Powiązanie</i><br>
&gt;&nbsp;żądanie&nbsp;&gt;<br>
&lt;&nbsp;wartość&nbsp;&lt;
</td>
<td>
<b>Tabela</b><br>
Zarejestruj<br>
Pole
</td>
</tr>
</tbody>
</table>

Jednak w wersji 10.0.15 i nowszych można skonfigurować pola modelu danych, które można wywoływać tylko wtedy, gdy podane są wartości skonfigurowanych parametrów. Gdy takie pole jest konfigurowane i wywoływane ze składnika formatu, wymagane parametry muszą być dostarczone w powiązaniu formatu jako argumenty wywołania. W takich przypadkach wartości argumentów można określić na podstawie wartości specyficznych dla formatu. W związku z tym można użyć dynamicznej **parametryzacji środowiska uruchomieniowego** dla wywołań modeli danych w celu obsługi poniższego przepływu danych.

<table>
<tbody>
<tr align="center">
<td>
<b>Format</b><br>
Element&nbsp;formatu&nbsp;1<br>
<br>
Element&nbsp;formatu&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Powiązanie</i><br>
&gt;&nbsp;żądanie&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;wartość&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;żądanie&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;wartość&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>mapowanie&nbsp;formatu</b><br>
Źródło&nbsp;danych&nbsp;1<br>
&nbsp;<br>
<b>value2=Func(value1)</b><br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Model&nbsp;danych</i><br>
&gt;&nbsp;pole1&nbsp;&gt;<br>
&lt;&nbsp;wartość&nbsp;1&nbsp;&lt;<br>
<b>&gt;&nbsp;pole2 (wartość2)&nbsp;&gt;</b><br>
&lt;&nbsp;wartość&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Mapowanie&nbsp;modelu</b><br>
Źródło&nbsp;danych&nbsp;1<br>
<br>
Źródło&nbsp;danych&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Powiązanie</i><br>
&gt;&nbsp;żądanie&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;wartość&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;żądanie&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;wartość&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Tabela&nbsp;1</b><br>
Rekord&nbsp;1<br>
Pole&nbsp;1<br>
<b>Tabela&nbsp;2</b><br>
Rekord&nbsp;2<br>
Pole&nbsp;2
</td>
</tr>
</tbody>
</table>

Nowa funkcjonalność pozwala na parametryzację wywołania do dowolnego pola modelu danych typu [*Rekord*](er-formula-supported-data-types-composite.md#record) lub [*Rekord listy*](er-formula-supported-data-types-composite.md#record-list). W parametrach pola modelu danych są obsługiwane następujące typy danych:

- [Wartość logiczna](er-formula-supported-data-types-primitive.md#boolean)
- [Kontener](er-formula-supported-data-types-composite.md#container)
- [Data](er-formula-supported-data-types-primitive.md#date)
- [Data/godzina](er-formula-supported-data-types-primitive.md#datetime)
- [GUID](er-formula-supported-data-types-primitive.md#guid)
- [Int64](er-formula-supported-data-types-primitive.md#int64)
- [Wartość całkowita](er-formula-supported-data-types-primitive.md#integer)
- [Rzeczywisty](er-formula-supported-data-types-primitive.md#real)
- [Ciąg](er-formula-supported-data-types-primitive.md#string)

Można określić każdy parametr pola modelu danych, dla którego argument może być podany jako jedna wartość zdefiniowanego typu danych i [*lista*](er-formula-supported-data-types-composite.md#record-list) takich wartości.

> [!NOTE]
> Domyślna wartość parametru pola modelu danych nie jest obsługiwana. Jeśli dodasz parametr do pola w modelu danych, a wersja tego modelu danych została już wydana i opublikowana, musisz [ponownie bazować](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) wszystkie odpowiednie mapowania i formaty modelu na nową wersję tego modelu, ponieważ ten model danych ulega zmianie nie jest kompatybilny wstecz.

Parametryczne pola modelu danych można skonfigurować w celu wywołania mapowań modeli specyficzne dla formatu. Takie podejście pomaga ograniczyć liczbę mapowań modeli, które należy skonfigurować dla wielu formatów jednego modelu danych. Możesz również użyć tego podejścia, aby poprawić wydajność wykonywania formatów i skrócić czas wymagany do wygenerowania dokumentów biznesowych. Wykonaj przykład z tego artykułu, aby dowiedzieć się więcej na temat tej funkcji.

## <a name="example-use-parameterized-calls-of-er-data-models"></a>Przykład: Użyj sparametryzowanych wywołań modeli danych ER

Poniższe kroki wyjaśniają, w jaki sposób użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zaprojektować rozwiązanie ER, które zawiera model danych, mapowanie modelu i składnik ER formatu, które są skonfigurowane do wywoływania mapowania modelu z formatu, dostarczając argument wywołania, którego wartość została obliczona w czasie wykonywania przy użyciu formuły formatu bieżącego. 

Kroki można wykonać na danych firmy **DEMF**. Modyfikacje kodu nie są wymagane. 

W tym przykładzie utworzysz wymagane [konfiguracje](general-electronic-reporting.md#Configuration) ER dla przykładowej firmy **Litware, Inc.**. Upewnij się, że dostawca konfiguracji dla przykładowej firmy **Litware, Inc.** (`http://www.litware.com`) jest wymieniony dla struktury ER i jest oznaczony jako **Aktywny**. Jeśli tego dostawcy konfiguracji nie ma na liście lub jeśli nie jest on oznaczony jako **aktywny**, wykonaj kroki opisane w temacie [Tworzenia dostawcy konfiguracji i zaznaczanie go jako aktywny](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="business-scenario"></a>Scenariusz biznesowy

Masz rozwiązanie ER, które zawiera format, który możesz uruchomić w celu wygenerowania dokumentu elektronicznego do celów audytu. Ten format zawiera transakcje podatkowe powiązane z zamówieniami sprzedaży i zamówieniami zakupu, które zawierają wymagane szczegóły, takie jak data transakcji i wartość podatku. Od nowego roku obrachunkowego struktura tego dokumentu uległa zmianie. Należy teraz przesłać rozszerzony dokument zawierający dodatkowe dane (nazwy) wszystkich stron (klientów i dostawców), których transakcje są prezentowane na wygenerowanych raportach. W związku z tym należy zmodyfikować rozwiązanie ER, aby generować dokumenty zgodne z tym nowym wymaganiem.

### <a name="configure-the-er-framework"></a>Konfigurowanie struktury ER

Wykonaj kroki opisane w sekcji [Konfigurowanie platformy ER](er-quick-start2-customize-report.md#ConfigureFramework), aby skonfigurować minimalny zestaw parametrów ER. Tę konfigurację należy ukończyć przed rozpoczęciem korzystania z platformy ER do projektowania nowego rozwiązania ER.

### <a name="design-a-domain-specific-data-model"></a>Projektowanie modelu danych specyficznego dla domeny

Musisz utworzyć nową konfigurację ER, która zawiera wymagany składnik modelu danych. Ten model danych będzie później używany jako źródło danych podczas projektowania formatu raportowania elektronicznego w celu wygenerowania raportu z inspekcji.

Aby zaimportować wymagany model danych z pliku XML dostarczonego przez firmę Microsoft, należy wykonać następujące kroki.

1. Pobierz [Przykładowy model audytu.wersja.1.xml](https://download.microsoft.com/download/7/1/9/719b0132-fed7-4c73-8afa-90cac29c2fee/Sample-audit-model.version.1.xml) i zapisz go na komputerze lokalnym.
2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
4. Na stronie **Konfiguracje**, w okienku akcji wybierz **Eksport** \> **Załaduj z pliku XML**.
5. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Przykładowy model audytu.wersja.1.xml**.
6. Wybierz przycisk **OK**, aby importować konfigurację.

    ![Zaimportowana konfiguracja modelu danych ER na stronie Konfiguracje.](./media/er-data-model-parameterized-calls-imported-model.png)

Poniższa ilustracja przedstawia edytowalną wersję skonfigurowanego modelu danych na stronie **Projektant modelu danych**.

![Struktura modelu danych ER na stronie projektanta modeli danych.](./media/er-data-model-parameterized-calls-model1.png)

Obecnie model jest przeznaczony do eksponowania tylko transakcji podatkowych, które posiadają wymagane szczegóły.

### <a name="design-a-model-mapping-for-the-configured-data-model"></a>Umożliwia zaprojektowanie mapowania modelu dla skonfigurowanego modelu danych

Jako użytkownik w roli Deweloper raportowania elektronicznego musisz utworzyć nową konfigurację raportowania elektronicznego, która zawiera składnik mapowania modelu dla przykładowego modelu danych inspekcji. Ten składnik implementuje skonfigurowany model danych dla Microsoft Dynamics 365 Finance i jest specyficzny dla tej aplikacji. Należy skonfigurować składnik mapowanie modelu, aby określić obiekty aplikacji, które muszą być używane do wypełniania skonfigurowanego modelu danych za pomocą danych aplikacji w czasie wykonywania. Aby wykonać to zadanie, musisz zrozumieć, w jaki sposób struktura danych domeny biznesowej podatku jest implementowana w Finance.

Wykonaj poniższe czynności, aby zaimportować wymagane mapowanie modelu z pliku XML dostarczonego przez firmę Microsoft.

1. Pobierz [Przykładowe mapowanie modelu audytu.wersja.1.1.xml](https://download.microsoft.com/download/c/0/3/c03a4673-b1b1-4ef8-96d0-bf96518be6e0/Sample-audit-model-mapping.version.1.1.xml) i zapisz go na komputerze lokalnym.
2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
4. Na stronie **Konfiguracje**, w okienku akcji wybierz **Eksport** \> **Załaduj z pliku XML**.
5. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Przykładowe mapowanie modelu audytu.wersja.1.1.xml**.
6. Wybierz przycisk **OK**, aby importować konfigurację.

    ![Zaimportowana konfiguracja mapowania modelu ER na stronie Konfiguracje.](./media/er-data-model-parameterized-calls-imported-mapping.png)

Poniższa ilustracja przedstawia edytowalną wersję skonfigurowanego mapowania modelu na stronie **Projektanta mapowania modeli**.

![Struktura mapowania modelu ER na stronie Projektant mapowania modelu.](./media/er-data-model-parameterized-calls-mapping1.png)

Obecnie mapowanie modelu ma na celu wyeksponowanie transakcji podatkowych, które mają wymagane szczegóły. Informacje są pobierane z tabeli aplikacji `TaxTrans` przy użyciu skonfigurowanych źródeł danych `TaxTrans` i źródeł danych ER `TaxTransFiltered`.

### <a name="design-a-new-format"></a>Zaprojektuj nowy format

Jako użytkownik pełniący rolę konsultanta funkcjonalnego raportowania elektronicznego należy utworzyć nową konfigurację ER zawierającą komponent formatu. Należy skonfigurować składnik formatu, aby wypełniać wygenerowane raporty transakcjami podatkowymi, które zawierają wszystkie wymagane szczegóły.

Wykonaj poniższe czynności, aby zaimportować wymagany format z pliku XML dostarczonego przez firmę Microsoft.

1. Pobierz [Przykładowy format audytu.wersja.1.1.xml](https://download.microsoft.com/download/e/b/7/eb7e126e-2bb3-4bbb-a735-ffd4c48920b1/Sample-audit-format.version.1.1.xml) i zapisz go na komputerze lokalnym.
2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
4. Na stronie **Konfiguracje**, w okienku akcji wybierz **Eksport** \> **Załaduj z pliku XML**.
5. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Przykładowy format audytu.wersja.1.1.xml**.
6. Wybierz przycisk **OK**, aby importować konfigurację.

    ![Zaimportowana konfiguracja formatu ER na stronie Konfiguracje.](./media/er-data-model-parameterized-calls-imported-format.png)

Poniższa ilustracja przedstawia edytowalną wersję skonfigurowanego formatu na stronie **Projektanta formatów**.

![Struktura formatu ER na stronie Projektant formatów.](./media/er-data-model-parameterized-calls-format1.png)

Format ER jest skonfigurowany do generowania raportu jako pliku tekstowego w formacie wartości rozdzielanych przecinkami (CSV).

### <a name="run-the-imported-format"></a>Uruchamianie zaimportowanego formatu

1. Na stronie **Konfiguracje** zaznacz konfigurację **przykładowego formatu** inspekcji, a następnie w okienku akcji wybierz opcję **Uruchom**.
2. W oknie dialogowym **Parametry raportu elektronicznego** na karcie **Rekordy do uwzględnienia** wybierz pozycję **Filtr**.
3. Określ warunki wybierania transakcji podatkowych w załącznikach **PIV-110000004** i **INV-10000001**.
4. Kliknij przycisk **OK**.
5. Kliknij przycisk **OK**.
6. Przejrzyj wygenerowany dokument zawierający transakcje podatkowe wybranych załączników.

    ![Podgląd wygenerowanego dokumentu z transakcjami podatkowymi.](./media/er-data-model-parameterized-calls-output1.png)

### <a name="adjust-the-imported-er-solution"></a>Dostosuj zaimportowane rozwiązanie ER

Zgodnie z nowym wymaganiem dokument, który należy przesłać, musi zawierać nazwy odbiorców i dostawców, których transakcje są uwzględnione. W związku z tym należy zmodyfikować zaimportowane rozwiązanie ER, tak aby generowało dokument zgodny z tym nowym wymaganiem.

Zdecyduj, jak mają zostać zaimplementowane wymagane modyfikacje importowanych składników ER.

Metoda ta ma na celu implementowanie następujących modyfikacji:

- W modelu danych dodaj nowe pole `Transaction.Party.Name` modelu danych typu *Ciąg*.
- W mapie modelowania powiązania danych dla nowego pola modelu, korzystając z relacji tabeli, zawiera dostęp do odpowiedniego rekordu tabeli `DirPartyTable` i pobiera z niej wartość aplikacji pola `Name`.

Chociaż to podejście działa, może to spowodować problemy z wydajnością w bazie danych SQL, ponieważ `TaxTrans` jest to tabela transakcji i dlatego może zawierać dużą liczbę rekordów. W takim przypadku liczba wywołań `DirPartyTable` musi być równa liczbie rekordów w tabeli `TaxTrans`, które mogą powodować problemy z wydajnością.

Można również wprowadzić następujące modyfikacje:

- W modelu danych dodaj nowy główny `Party` i nowe pole `Party.Name`.
- W mapowaniu modelu dodaj nowe źródło danych, które połączy wszystkie rekordy tabel używane w relacjach tabel w celu uzyskania dostępu do odpowiedniego rekordu tabeli aplikacji `DirPartyTable`, począwszy od `TaxTrans` tabeli.

Chociaż ta metoda działa, może to spowodować problemy ze zużyciem pamięci. Nawet jeśli nowe źródło [danych JOIN](er-join-data-sources.md) jest uruchamiane jako jedno żądanie SQL do bazy danych aplikacji w celu uniknięcia problemów z wydajnością bazy danych, wynik musi zostać pobrany do pamięci serwera aplikacji. Ponieważ liczba rekordów i liczba pól w tych rekordach będzie dosyć duża, ta metoda może spowodować bardzo duże zużycie pamięci. Może nawet zostać zgłoszony wyjątek dotyczący braku pamięci.

Modyfikacje można wprowadzić, gdy działający format gromadzi w pamięci unikalne kody identyfikacyjne klientów i dostawców dla wszystkich transakcji podatkowych, które będą prezentowane w wygenerowanym raporcie. Ponieważ powinny być zachowywane tylko unikatowe kody, końcowy zestaw kodów nie będzie na tyle duży, aby wpływać na zużycie pamięci. Zestaw kodów zostanie przekazany do mapowania modelu jako argument innego wywołania źródła danych typu *Model*. Na podstawie tego wywołania mapowanie modelu będzie uruchamiać nowe źródło danych ER, które wykonuje pojedyncze żądanie SQL do bazy danych aplikacji, aby pobrać z tabeli `DirPartyTable` tylko rekordy tych stron, których kody są prezentowane w dostarczonym zestawie kodów.

### <a name="adjust-the-imported-data-model"></a>Dostosuj importowany model danych

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Przykładowy model audytu**.
3. Na skróconej karcie **wersje** wybierz wersję **2** ze stanem **Wersja robocza**.
4. Wybierz **składniki konfiguracji** skróconej karcie.
5. Wybierz **Projektant**, aby otworzyć model danych do edycji.
6. Na stronie **Model** danych upewnij się, że pole `Root` jest zaznaczone, a następnie wybierz pozycję **Nowy**.
7. W oknie dialogowym rozwijanym wykonaj następujące kroki:

    1. W grupie **pól Nowy węzeł** wybierz element **podrzędny węzła** aktywnego.
    2. W polu **Nazwa** wprowadź nazwę **Strona**.
    3. W polu **Kod przedmiotu** wybierz **Lista tabel**.
    4. Wybierz przycisk **Dodaj**, aby dodać nowe pole obliczeniowe.

8. Upewnij się, że pole `Root.Party` jest zaznaczone, a następnie na karcie **Węzeł** wybierz **Parametry**.
9. W oknie dialogowym **Parametry** wykonaj następujące kroki:

    1. Na karcie **Parametry** wybierz pozycję **Nowy**.
    2. W polu **Nazwa** wpisz **PartyRefRecId**.
    3. W polu **Typ** wybierz **Int64**.
    4. Zaznacz pole wyboru **Lista**.
    5. Wybierz **przycisk OK**, aby zakończyć wprowadzanie parametrów.

    > [!NOTE]
    > Właśnie skonfigurowano pole modelu danych `Root.Party` jako pole, które jest wywoływane, gdy wartość jest dostarczana w parametrze **PartyRefRecId**. Ta wartość musi znajdować się na liście rekordów zawierających `Value` pole *typu danych Int64*.

    ![Okno dialogowe Parametry.](./media/er-data-model-parameterized-calls-model2a.png)

10. Upewnij się, że pole `Root.Party` jest nadal zaznaczone, a następnie wybierz **Nowy**.
11. W oknie dialogowym rozwijanym wykonaj następujące kroki:

    1. W grupie **pól Nowy węzeł** wybierz element **podrzędny węzła** aktywnego.
    2. Wprowadź **nazwę** w polu, wpisz **Nazwa**.
    3. W polu **Typ przedmiotu** wybierz **Ciąg**.
    4. Wybierz przycisk **Dodaj**, aby dodać nowe pole obliczeniowe.

12. Wybierz **Zapisz** i zamknij stronę **Model danych**.

    ![Struktura dostosowanego modelu danych ER na stronie Projektant modelu danych.](./media/er-data-model-parameterized-calls-model2b.png)

13. Na skróconej karcie **Wersje** dla wersji **2** wybierz **Zmień stan** \> **Zakończono**. Następnie wybierz opcję **OK**.

    > [!NOTE]
    > Zmiany modelu danych są przechowywane w drugiej wersji składnika modelu danych **Przykładowy model inspekcji**, który znajduje się w drugiej wersji konfiguracji ER **modelu inspekcji przykładowego**.

![Zaktualizowano konfigurację modelu danych ER na stronie Konfiguracje.](./media/er-data-model-parameterized-calls-updated-model.png)

### <a name="adjust-the-imported-model-mapping"></a>Dostosuj mapowanie importowanego modelu

1. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz **Przykładowy model audytu**.
2. Wybierz **Przykładowe mapowanie modelu kontroli**, a następnie na **Wersje** skróconej karty wybierz drugą wersję mapowania opartą na pierwszej wersji modelu danych (wersja **1,2**), a ma status **Wersja robocza**.
3. Wybierz opcję **Zmień podstawę**.
4. W polu **Wersja docelowa** pozostaw wersję **2** modelu **podstawowego przykładowego modelu** inspekcji.
5. Wybierz **przycisk OK**, aby ponownie ustawić bazę i dostosować mapowanie modelu do najnowszych zmian modelu danych.

    Zauważ, że numer wersji twojego edytowalnego mapowania modelu został zmieniony z **1,2** na **2,2**, aby wskazać, że druga wersja modelu jest obecnie używana jako podstawa.

6. Wybierz opcję **Konstruktor**.
7. Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Modelowanie do mapowania źródła danych** dla bieżącego mapowania modelu.
8. Aby dodać nowe źródło danych w celu uzyskania dostępu do tabeli aplikacji `DirPartyTable`, należy wykonać następujące kroki:

    1. W okienku **Typy źródła danych** wybierz opcję **Dynamics 365 for Operations \> Rekordy tabeli**.
    2. W okienku **Źródła danych** wybierz **Dodaj źródło**.
    3. W polu **Nazwa** wpisz **PartyTable**.
    4. W polu **Tabela** wprowadź **DirPartyTable**.
    5. Wybierz przycisk **OK**, aby zakończyć dodawanie nowego źródła danych.

9. Aby na podstawie podanej listy kodów identyfikacyjnych rekordów dodać nowe źródło danych do rekordów żądań `DirPartyTable`, należy wykonać następujące kroki:

    1. W okienku **Typ źródła danych** rozwiń opcję **Ogólne \> Pusty kontener**.
    2. W okienku **Źródła danych** wybierz **Dodaj źródło**.
    3. Wprowadź **nazwę** w polu, wpisz **Dane**.
    4. Wybierz przycisk **OK**, aby zakończyć dodawanie nowego źródła danych.
    5. W panelu **Źródła danych** rozwiń źródło danych **Dane**.
    6. W okienku **Typ źródła danych** wybierz **Funkcje \> Pole obliczeniowe**.
    7. Wybierz opcję **Pole** w okienku **Dodaj**.
    8. W polu **Nazwa** wpisz **DirParty**.
    9. Wybierz opcję **Edytuj formułę**.
    10. Na stronie **Projektant formuł** wybierz **Parametry**.
    11. W oknie dialogowym **Parametry** wykonaj następujące kroki:

        1. Na karcie **Parametry** wybierz pozycję **Nowy**.
        2. W polu **Nazwa** wpisz **DirPartyId**.
        3. W polu **Typ** wybierz **Int64**.
        4. Zaznacz pole wyboru **Lista**.
        5. Kliknij przycisk **OK**.

        > [!NOTE]
        > Właśnie skonfigurowałeś to pole obliczeniowe tak, aby w czasie wykonywania akceptowało argument pojedynczego parametru skonfigurowanego jako lista rekordów zawierająca pojedyncze pole `Value` typu *Int64*.

    12. W polu **Formuła** wprowadź następujące wyrażenie:

        `FILTER(PartyTable, VALUEINLARGE(PartyTable.RecId, DirPartyId, DirPartyId.Value))`

        > [!NOTE]
        > Właśnie skonfigurowano pole obliczeniowe `DirParty` do pobierania tylko rekordów `DirPartyTable`, w których kody identyfikujące rekordy są zawarte na liście `DirPartyId`, która jest dostarczana jako argument, gdy wywoływane jest pole `DirParty`.

        ![Formuła do pobrania nazw stron z tabeli aplikacji na stronie projektanta formuł.](./media/er-data-model-parameterized-calls-formula1.png)

    13. Wybierz **Zapisz** oraz zamknij stronę **Projektowanie formuły**.
    14. Wybierz **przycisk Zapisz**, a następnie wybierz przycisk **OK**, aby zakończyć dodawanie nowego źródła danych.

10. Aby powiązać nowe źródło danych z polem nowego modelu danych, należy wykonać następujące kroki, aby model danych uwidaczniał nazwy stron:

    1. W polu **Model danych** wybierz pozycję Model danych `Root.Party`.
    2. W okienku **Model danych** wybierz **Edytuj**.
    3. Na stronie **Projektant formuł** wprowadź w polu **Formuła** następującą wartość `Data.DirParty(PartyRefRecId)`.
    4. Wybierz **Zapisz** oraz zamknij stronę **Projektowanie formuły**.

        > [!NOTE]
        > Właśnie skonfigurowano powiązanie, aby wywołać skonfigurowane źródło danych `Data.DirParty` i podać listę kodów identyfikacyjnych rekordów, które zostaną określone w formacie po wywołaniu pola modelu danych `Root.Party`.

    5. W polu **Model danych** wybierz pozycję Model danych `Root.Party.Name`.
    6. W okienku **Model danych** wybierz **Edytuj**.
    7. Na stronie **Projektant formuł** modelu w okienku **Typy źródła danych** wybierz **Dane \> DirParty** i **Nazwa**.
    8. Wybierz **Dodaj źródło danych**.
    9. Wybierz **Zapisz** oraz zamknij stronę **Projektowanie formuły**.

    ![Struktura dostosowanego mapowania modelu ER na stronie Projektant mapowania modelu.](./media/er-data-model-parameterized-calls-mapping2.png)

11. Wybierz **Zapisz** i zamknij stronę **Projektant mapowania modelu**.
12. Zamknij stronę **Mapowanie modelu do źródła danych**.
13. Na skróconej karcie **Wersje** dla wersji **2,2** wybierz **Zmień stan \> Zakończono**. Następnie wybierz opcję **OK**.

### <a name="adjust-the-imported-format"></a>Dostosuj importowany format

1. Na stronie **Konfiguracje** wybierz opcję **Przykładowy format audytu**.
2. Na skróconej karcie **wersje** wybierz wersję **1,2** ze stanem **Wersja robocza**.
3. Wybierz opcję **Zmień podstawę**.
4. W polu **Wersja docelowa** pozostaw wersję **2** modelu **podstawowego przykładowego modelu** inspekcji.
5. Wybierz **przycisk OK**, aby zmienić bazę i dostosować format do ostatnich zmian modelu danych.
6. Wybierz opcję **Konstruktor**.
7. Na stronie **Projektant formatów** w drzewie struktury formatu w lewym okienku wybierz **Rozwiń/Zwiń**.
8. Wykonaj poniższe czynności, aby dodać nowy element formatu do zbierania kodów identyfikacyjnych rekordów stron, których transakcje są prezentowane na generowanych raportach.

    1. W drzewie struktury formatu wybierz element sekwencji **Report.Row.Trans**.
    2. Wybierz opcję **Dodaj**.
    3. W oknie dialogowym **Dodaj** wybierz **źródła danych \> Pozycja**.
    4. W oknie dialogowym **Właściwości składnika** w polu **Nazwa** wpisz **Identyfikator**.
    5. W polu **Typ danych** wybierz opcję **Int64**.
    6. Kliknij przycisk **OK**.

    > [!NOTE]
    > Element **Źródło danych \> Przedmiot** może być używany do wykonywania wewnętrznych obliczeń i transformacji danych tylko w zakresie bieżącego formatu. W związku z tym dodanie tego elementu formatu nie zmieni zawartości wygenerowanego dokumentu.

9. Aby dodać nowe elementy formatu w celu wprowadzenia nazw stron w generowanych raportach, należy wykonać następujące kroki:

    1. Wybierz element **Report.Row** sequence.
    2. Wybierz opcję **Dodaj**.
    3. W oknie dialogowym **Dodaj** wybierz opcję **Tekst \> Sekwencja**.
    4. W oknie dialogowym **Właściwości składnika** w polu **Nazwa** wpisz **Strona**.
    5. Kliknij przycisk **OK**.
    6. Wybierz element **Report.Row.Party** sequence.
    7. Wybierz opcję **Dodaj**.
    8. W oknie dialogowym **Dodaj** wybierz opcję **Tekst \> Ciąg**.
    9. W oknie dialogowym **Właściwości składnika** w polu **Nazwa** wpisz **Nazwa**.
    10. Kliknij przycisk **OK**.

10. Wykonaj poniższe kroki, aby dodać nowe źródło danych w celu zbierania kodów identyfikacyjnych rekordów stron, których transakcje są prezentowane w generowanych raportach:

    1. Na karcie **mapowanie** wybierz opcję **Dodaj korzeń**.
    2. W oknie dialogowym **Dodawanie źródła danych** wybierz kolejno pozycje **Funkcje \> Zbieranie danych**.
    3. W oknie dialogowym **Właściwości źródła danych zbieranie danych** w polu **Nazwa** wprowadź wartość **PartyIds**.
    4. W polu **Typ elementu** wybierz opcję **Int64**.
    5. Kliknij przycisk **OK**.

11. Wykonaj poniższe czynności, aby dodać nowe powiązanie do zbierania kodów identyfikujących rekordy stron, których transakcje są prezentowane na wygenerowanych raportach:

    1. W drzewie struktury formatu wybierz element danych **Report.Row.Trans.Id**.
    2. Wybierz opcję **Edytuj formułę**.
    3. Na stronie Projektant **formuł** wprowadź wyrażenie `PartyIds.Collect(model.Transaction.Party.RecId)`.
    4. Wybierz **Zapisz** oraz zamknij stronę **Projektowanie formuły**.

12. Wykonaj następujące kroki, aby dodać nowe powiązania i wprowadzić nazwy stron w wygenerowanych raportach:

    1. W drzewie struktury formatu wybierz element sekwencji **Report.Party**.
    2. Wybierz opcję **Edytuj formułę**.
    3. Na stronie Projektant **formuł** wprowadź wyrażenie `model.Party(PartyIds.Result)`.
    4. Wybierz **Zapisz** oraz zamknij stronę **Projektowanie formuły**.
    5. W drzewie struktury formatu wybierz element sekwencji **Report.Party.Name**.
    6. Na karcie **Mapowanie** wybierz opcję `model.Party.Name`.
    7. Wybierz **Powiąż**.

    ![Struktura dostosowanego formatu ER na stronie Projektant formatu.](./media/er-data-model-parameterized-calls-format2.png)

13. Wybierz **Zapisz** oraz zamknij stronę **Projektant formatów**.
14. Zamknij stronę **Mapowanie modelu do źródła danych**.
15. Na skróconej karcie **Wersje** dla wersji **2.2** wybierz **Zmień stan** \> **Zakończono**. Następnie wybierz opcję **OK**.

### <a name="run-the-adjusted-format"></a>Uruchom dostosowany format

1. Na stronie **Konfiguracje** zaznacz **przykładowy format** inspekcji, a następnie w okienku akcji wybierz opcję **Uruchom**.
2. W oknie dialogowym **Parametry raportu elektronicznego** na karcie **Rekordy do uwzględnienia** wybierz pozycję **Filtr**.
3. Określ warunki wybierania transakcji podatkowych w załącznikach **PIV-110000004** i **INV-10000001**.
4. Kliknij przycisk **OK**.
5. Kliknij przycisk **OK**.
6. Przejrzyj wygenerowany dokument, który zawiera transakcje podatkowe wybranych załączników oraz nazwy odpowiednich odbiorców i dostawców.

    ![Podgląd wygenerowanego dokumentu z transakcjami podatkowymi i nazwami stron.](./media/er-data-model-parameterized-calls-output2.png)

7. Przejdź do **Rozrachunki z dostawcami** \> **Dostawcy** \> **Wszyscy dostawcy** i przejrzyj szczegóły wybranego kuponu **PIV-110000004**, w tym nazwę dostawcy .

    ![Przeglądanie szczegółów kuponu zakupu na stronach Wszyscy dostawcy i Arkusz faktury.](./media/er-data-model-parameterized-calls-review1.gif)

8. Przejdź do **Rozrachunki z odbiorcami** \> **Klienci** \> **Wszyscy klienci** i przejrzyj szczegóły wybranego kuponu **INV-10000001**, w tym nazwę klienta.

    ![Przeglądanie szczegółów załącznika sprzedaży na stronach Wszyscy odbiorcy i Zaksięgowane podatki.](./media/er-data-model-parameterized-calls-review2.gif)

Aby uzyskać więcej informacji na temat tego wykonania rozwiązania ER, użyj wbudowanego [śledzenia wydajności](trace-execution-er-troubleshoot-perf.md) parsera

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Obsługuj sparametryzowane wywołania źródeł danych ER typu pola obliczeniowego](er-calculated-field-type.md)
- [Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md)
- [Korzystanie ze źródeł danych DATA COLLECTION w formatach raportowania elektronicznego](er-data-collection-data-sources.md)
- [Funkcja ValueInLarge ER](er-functions-logical-valueinlarge.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
