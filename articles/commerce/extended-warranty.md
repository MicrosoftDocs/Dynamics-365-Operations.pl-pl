---
title: Utwórz i skonfiguruj rozszerzone gwarancje
description: W tym temacie opisano rozszerzone gwarancje i sposób ich tworzenia i konfigurowanie w Microsoft Dynamics 365 Commerce.
author: sijoshi
manager: annbe
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: sijoshi
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 411895763cc282766b5a668208f20c72496059cd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965127"
---
# <a name="create-and-configure-extended-warranties"></a>Utwórz i skonfiguruj rozszerzone gwarancje

[!include [banner](includes/banner.md)]

W tym temacie opisano rozszerzone gwarancje i sposób ich tworzenia i konfigurowanie w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Klienci w coraz większym stopniu wybierają rozszerzone wsparcie i usługi podczas kupowania produktów, a zwłaszcza produktów konsumenckich sprzedawanych po cenach specjalnych, takich jak telefony i komputery. Dostarczając rozszerzone gwarancje zakupu, detaliści mogą ułatwić budowanie lojalności odbiorców. Rozszerzone gwarancje umożliwiają klientom zapoznanie się z możliwością serwisowania i pomocy technicznej. Dzięki temu klienci mogą mieć pewność, że ich problemy będą skutecznie obsługiwane.

Rozszerzone gwarancje mogą być sprzedawane odbiorcom w kanale detalicznym podczas początkowego zakupu produktu. Mogą być również sprzedawane przez ograniczony czas po pierwszym zakupie.

### <a name="warranty-item-setup"></a>Ustawienia pozycji gwarancji

Dynamics 365 Commerce udostępnia funkcje umożliwiające tworzenie pozycji gwarancji i określanie jej atrybutów. Te atrybuty obejmują związek między produktem a pozycją gwarancji, cenę gwarancji oraz czas trwania gwarancji. Po skonfigurowaniu i zwolnieniu towaru gwarancyjnego do jednostki organizacyjnej sprzedawca może sprzedawać gwarancje za pośrednictwem Modern Point of Sale (MPOS), sklepów internetowych i innych kanałów detalicznych.

### <a name="warranty-item-sales"></a>Sprzedaż pozycji gwarancji

Rozszerzone gwarancje są być sprzedawane w kanale detalicznym podczas początkowego zakupu produktu. Mogą być również sprzedawane przez ograniczony czas po pierwszym zakupie.

W punkcie sprzedaży (POS) sprzedawca jest monitowany o dodanie rozszerzonej gwarancji po dodaniu pokrewnego produktu do koszyka odbiorcy. Dlatego możliwość sprzedaży po wyższej cenie lub sprzedaży powiązanej jest prezentowana sprzedawcom jako część przepływu sprzedaży.

Klienci mogą również wrócić się później i zakupić rozszerzoną gwarancję na produkt, który wcześniej zakupiono. W takich przypadkach sprzedawca może wyszukać oryginalną transakcję i sprzedać odbiorcy powiązaną przedłużoną gwarancję pozycji.

### <a name="warranty-terminology"></a>Terminologia gwarancji

Poniższa tabela określa niektóre terminy związane z gwarancjami.

| Okres | opis |
|------------------------------|--------------|
| Rozszerzona gwarancja/gwarancja | *Gwarancja rozszerzona* dotyczy umowy serwisowej lub umowy, która stanowi przedłużoną gwarancję dla klientów. Przedłużona gwarancja obejmuje dodatkową usługę wymiany lub naprawy towarów w okresie obowiązywania przedłużonej gwarancji. |
| Gwarancja producenta | *Gwarancja producenta* (często określana jako *gwarancja ograniczona*) jest gwarancją, którą klienci otrzymają w momencie zakupu produktu. Oto niektóre funkcje gwarancji producenta:<ul><li>Koszty gwarancji są uwzględniane w kosztach produktu. Klienci nie muszą płacić żadnej dodatkowej kwoty z tytułu gwarancji producenta.</li><li>W zależności od kategorii produktu gwarancja producenta zazwyczaj trwa 30 dni, sześć miesięcy lub rok. (W przypadku większości elektroniki konsumenckiej gwarancja wynosi jeden rok.)</li><li>Gwarancja obejmuje wszelkie wady spowodowane awariami mechanicznymi lub elektrycznymi. Zakres obowiązywania jest ograniczony i nie obejmuje on żadnych przypadkowych szkód w zakupionym produkcie. Klienci, którzy chcą chronić produkty nabyte w wyniku codziennych szkód, powinni inwestować w przedłużoną gwarancję. Rozszerzone gwarancje z ostatnich dwóch do dziesięciu lat, zależnie od kategorii produktów. Mają również szerszy zasięg i obejmują codzienne nieszczęścia, takie jak spadającce krople, wylane ciecze i plamy.</li></ul> |
| Pozycja objęta gwarancją | *Pozycja gwarancji* to rozszerzona pozycja gwarancji, która jest sprzedawana dla pozycji, której dotyczy to zapotrzebowanie. Przykładem jest dwuletni plan ochrony przed przypadkami dla komputerów przenośnych. |
| Pozycja podlegająca gwarancji | *Pozycja podlegająca gwarancji* jest serializowanym produktem, na który sprzedawana jest gwarancja. Na przykład laptop jest pozycją podlegającą gwarancji, na który sprzedawane są dwuletnie i trzyletnie przedłużone gwarancje. |
| Grupa gwarancyjna | *Grupa gwarancyjna* jest relacją między pozycje gwarancyjne i pozycje podlegające gwarancji. POS używa grup gwarancji, aby określić, które pozycje gwarancji powinny być w monicie o dodanie przez sprzedawców, gdy do koszyka klienta zostanie dodany przedmiot objety gwarancją. |
| Zasady gwarancji | *Zasady gwarancji* to jednostka utworzona w handlu w przypadku sprzedaży polis gwarancyjnych. Zasady gwarancji obejmują takie informacje, jak data początkowa i końcowa nabytego przedmiotu gwarancyjnego, warunki i warunki oraz numer seryjny produktu, którego dotyczy zamówienie. Numery polis gwarancyjnych mogą być współużytkowane z odbiorcami w taki sposób, aby zawierały odniesienie do zakupionych przez nich towarów o rozszerzonej gwarancji. |

## <a name="create-a-warranty-item"></a>Tworzenie pozycji gwarancji

Aby utworzyć towar objęty gwarancją w Commerce, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Retail and Commerce \> Produkty i kategorie \> Produkty**.
1. Wybierz pozycję **Nowy**, aby utworzyć pozycję gwarancji.
1. W oknie dialogowym **Nowy produkt** w polu **Typ produktu** wybierz opcję **Serwis**.
1. W polu **Podtyp produktu** wybierz **Produkt**.
1. W polu **Typ serwisu produktu** wybierz **Serwis**.
1. W polu **Nazwa produktu** wprowadź nazwę produktu.
1. W polu **Kategoria sieci sprzedaży** wybierz wartość w oknie dialogowym rozwijanym, a następnie kliknij przycisk **OK**.
1. W polu **Numer produktu** wprowadź numer produktu.
1. Kliknij przycisk **OK**.
1. Na stronie **Szczegóły produktu**, na skróconej karcie **Gwarancja**, określ pola **Jednostka czasu** i **Długość czasu**.

    | Nazwa pola | Wartość | opis |
    |------------|-------|-------------|
    | Jednostka czasu | **Dni**, **tygodnie**, **miesiące** lub **lata** | W tym polu jest określana jednostka czasu używana dla gwarancji. |
    | Czas | Dodatnia wartość całkowita | To pole określa czas trwania gwarancji w wybranej jednostce czasu. |

    Na przykład w przypadku dwuletniej gwarancji należy określić pole **Jednostka czasu** jako **Lata** i pole **Długość czasu** na **2**. Można również ustawić pole **Jednostka czasu** na **Miesiące** i pole **Długość czasu** na **24**, jak to pokazano na poniższej ilustracji.

    ![Strona szczegółów produktu dla pozycji gwarancji](./media/ew-time-properties.png)

1. Wybierz **Zapisz**, aby zapisać pozycję gwarancji.
1. Zwolnij produkt gwarancyjny do firmy, aby można było go sprzedać. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie produktów handlu detalicznego](set-up-retail-products.md).
1. Na stronie **Szczegóły zwolnionego produktu**, na skróconej karcie **Gwarancja**, należy określić pola **Postawa przedziału cenowego**, **Dolny limit** i **Górny limit**.

    | Nazwa pola | Wartość | opis |
    |------------|-------|-------------|
    | Podstawa przedziału cenowego | **Brak**, **Cena podstawowa** lub **Cena sprzedaży** | <ul><li>**Brak** — wartości **Dolny limit** i **Górny limit** zakresów cen nie mają zastosowania.</li><li>**Cena podstawowa** — dana gwarancja będzie stosowana, jeśli cena podstawowa (czyli cena bez rabatu) dla pozycji objętej gwarancją, jest pomiędzy wartościami **Doly limit** i **Górny limit** określonymi w tym miejscu, na podstawie ceny pozycji podlegającej gwarancji.</li><li>**Cena sprzedaży** — Ta wartość jest zarezerwowana do wykorzystania w przyszłości.</li></ul> |
    | Dolny limit, górny limit | Dodatnia wartość całkowita | Te pola definiują górny i dolny limit cen dla przedmiotu, którego dotyczy oferta, oraz sposób, w jaki bieżący towar objęty gwarancją jest dostępny dla pozycji, którą można uzasadnić. Ograniczenia te mogą być oparte na podstawowej cenie danego towaru (znanej również jako sugerowana przez producenta cena detaliczna \[MSRP\]). Jeśli w polu **Podstawowy przedział cenowy** jest ustawiona wartość **Cena podstawowa**, tylko pozycja objęta gwarancją (produkt) o cenie podstawowej między wartościami **Dolny limit** i **Górny limit** będzie wyzwalał monit o dodanie pozycji gwarancji w punkcie sprzedaży. |

    Na przykład na poniższej ilustracji pokazano pole **Postawa przedziału cenowego** ustawione na wartość **Cena podstawowa**, pole **Dolny limit** jest ustawione na 500$ a pole **Górny limit** jest ustawione na 1000$.
    
    ![Strona szczegółów wydanego produktu dla pozycji gwarancji](./media/ew-release-product-details.png)

1. Asortyment pozycji gwarancyjnej dla kanału, w którym zostanie on sprzedany. Aby uzyskać więcej informacji, zobacz [Konfigurowanie asortymentów](set-up-assortments.md).

### <a name="example"></a>Przykład

Laptop, który jest pozycją objętą gwarancją (produkt), ma cenę podstawową 999$, a istnieją dwie pozycji gwarancji na laptop:

- Gwarancja\_1 ma dolny limit 500$ i górny limit 1000$, a pole **Postawa przedziału cenowego** jest ustawione na wartość **Cena podstawowa**.
- Gwarancja\_2 ma dolny limit 1001$ i górny limit 2000$, a pole **Postawa przedziału cenowego** jest ustawione na wartość **Cena podstawowa**.

W takim przypadku, gdy do koszyka odbiorcy zostanie dodany element z gwarancją typu laptop, monit o dodanie gwarancji\_1 będzie widoczny w punkcie sprzedaży, ponieważ cena komputera przenośnego mieści się między dolnym a górnym limitem gwarancji\_1.

> [!NOTE]
> Jeśli w tym przykładzie mają być wyświetlane monity dotyczące gwarancji\_1 i gwarancji\_2, niezależnie od ceny towarów podlegających zatwierdzeniu, należy w polu **Postawa przedziału cenowego** ustawić wartość **Brak**.

## <a name="configure-channel-specific-settings"></a>Konfigurowanie ustawień specyficznych dla kanału

Ustawienia specyficzne dla kanału umożliwiają określenie, czy monit o dodanie towaru gwarancyjnego powinien być wyświetlany w punkcie sprzedaży, gdy do koszyka odbiorcy zostanie dodany towar objęty gwarancją.

Aby skonfigurować ustawienia specyficzne dla kanału w module Commerce, należy wykonać następujące kroki.

1. Przejdź do **Retail i Commerce \> Produkty i kategorie \> Gwarancja \> Ustawienia gwarancji**.
1. Na karcie **Specyficzne dla kanału** w kolumnie **Monit dotyczący gwarancji** dla kanału postępuj zgodnie z następującymi krokami:

    - To pole wyboru należy zaznaczyć, jeśli monit dotyczący pozycji gwarancji ma być wyświetlany w punkcie sprzedaży w momencie dodania do koszyka pozycji, której dotyczy to warunki.
    - To pole wyboru należy odznaczyć, jeśli monit dotyczący pozycji gwarancji nie ma być wyświetlany w punkcie sprzedaży w momencie dodania do koszyka pozycji, której dotyczy to warunki.

1. Uruchom zadanie **1070**, aby zsynchronizować dane z kanałem.

## <a name="configure-a-number-sequence-for-warranty-policies"></a>Skonfiguruj sekwencję numerów dla zasad gwarancji

Każda zasada gwarancji jest jednoznacznie identyfikowana przez numer zasad dotyczących gwarancji generowany przez sekwencję numerów. Aby uzyskać więcej informacji na temat sekwencji numerów, zobacz temat pomocy [Omówienie sekwencji numerów](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Aby skonfigurować sekwencję numerów dla zasad gwarancji w Commerce, należy wykonać następujące kroki.

1. Przejdź do **Retail i Commerce \> Produkty i kategorie \> Gwarancja \> Ustawienia gwarancji**.
1. Na karcie **Sekwencje numerów** w wierszu odniesienia **Polityka gwarancyjna** wprowadź lub wybierz wartość w polu **Kod sekwencji numerów**.

## <a name="set-up-a-warranty-group"></a>Ustawianie grupy gwarancji

Grupa gwarancyjna jest relacją między pozycje gwarancyjne i pozycje podlegające gwarancji. POS używa grup gwarancji, aby określić, które pozycje gwarancji powinny być w monicie o dodanie przez sprzedawców, gdy do koszyka klienta zostanie dodany przedmiot objety gwarancją.

Aby skonfigurować przypisanie grupy gwarancji w Commerce, należy wykonać następujące czynności.

1. Przejdź do **Retail i Commerce \> Produkty i kategorie \> Gwarancja \> Grupy gwarancji**.
1. Wybierz pozycję **Nowy**, aby utworzyć grupę gwarancji.
1. W polu **Nazwa** wprowadź nazwę nowej grupy.
1. Na skróconej karcie **Ogólne** w polu **Opis** wpisz opis grupy.
1. Na skróconej karcie **Pozycje gwarancji** wybierz opcję **Dodaj wiersz**, aby dodać pozycję gwarancji.
1. W polu **Kolejność wyświetlania** wprowadź numer klasyfikacji grupy gwarancyjnej w punkcie sprzedaży. Pozycje dotyczące gwarancji są pokazywane w punkcie sprzedaży w kolejności rosnącej rangi w monicie gwarancji.
1. Na skróconej karcie **Pozycje objęte gwarancją** wybierz opcję **Dodaj wiersz**, aby dodać pozycję objętą gwarancją.
1. Jeśli pozycja gwarancji dotyczy całej kategorii towarów, które są obięte gwarancją (produkty), wybierz kategorię w polu **Kategoria**. Jeśli pozycja gwarancji dotyczy konkretnego towaru, który jest objęty gwarancją (produkt), należy wybrać produkt w polu **Produkt**.
1. Na skróconej karcie **Odpowiednie kanały** wybierz opcję **Dodaj wiersz**, aby dodać kanał, w którym chcesz sprzedać pozycje gwarancji.
1. Wybierz **Zapisz**, aby zapisać konfigurację.
1. Wybierz opcję **Publikuj**, aby opublikować grupę gwarancji.
1. Uruchom zadanie **1040**, aby zsynchronizować dane z kanałem.

## <a name="sell-warranty-items-at-the-pos"></a>Sprzedaj pozycje gwarancyji w punkcie sprzedaży

Dwie operacje POS pozwalają sprzedawcą sprzedawać pozycje gwarancyji podczas przepływu pracy dla zakupów klientów:

- **Dodaj gwarancję** — Ta operacja powoduje wyzwolenie monitu pokazującego stosowne gwarancje dla pozycji objętej gwarancją, która jest wybrana w koszyku.
- **Dodaj gwarancję do istniejącej transakcji** — Ta operacja pozwala sprzedawcy sprzedać gwarancję na pozycję objętą gwarancją, która została sprzedana wcześniej. Sprzedawcy mogą znaleźć oryginalną transakcję dla pozycji objętej gwarancją, wprowadzając numer paragonu transakcji.

Na poniższej ilustracji pokazano przykład strony terminalu w punkcie sprzedaży z monitem o dodanie pozycji gwarancji w odniesieniu do bieżącego zakupu pozycji objętej gwarancją.

![Przykład monitu o dodanie pozycji gwarancji dla bieżącego zakupu](./media/ew-sell-warranty.png)

Na poniższej ilustracji przedstawiono przykład funkcji służącej do dodawania pozycji gwarancji do pozycji objętej gwarancją, która została wcześniej sprzedana.

![Przykładowa funkcja dodawania pozycji gwarancji dla wcześniej sprzedanej pozycji objętej gwarancją](./media/ew-add-warranty-existing.png)

## <a name="process-warranty-transactions"></a>Przetwarzanie transakcji gwarancyjnych

Jeśli gwarancje są sprzedawane w transakcjach kasowych, po zaksięgowaniu transakcji w Commerce Headquarter, użytkownicy Commerce mogą uruchomić zadanie **Przetwarzaj transakcje gwarancyjne** w celu przetworzenia transakcji gwarancyjnych i utworzenia zasad dotyczących gwarancji.

Aby przetworzyć transakcje gwarancyjne w Commerce headquarters, wykonaj następujące kroki.

1. Przejdź do **Retail i Commerce \> Produkty i kategorie \> Gwarancja \> Przetwarzaj transakcje gwarancyjne**.
1. W oknie dialogowym **Wybór węzłów organizacji** wybierz wartość w polu **Hierarchia organizacyjna**.
1. Na liście **Dostępne węzły organizacji** wybierz pojedynczy sklep lub, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów, węzeł.
1. Wybierz przycisk strzałki w prawo, aby dodać swój wybór do listy **Wybrane węzły organizacji**.
1. Wybierz kartę **Uruchom w tle**.
1. Dla opcji **Przetwarzania wsadowego** określ wartość **Tak**, a następnie wybierz pozycję **Cykl**.
1. W oknie dialogowym **Definiowanie cyklu** w polu **Data rozpoczęcia** wybierz lub wprowadź datę rozpoczęcia cyklu.
1. W polu **Godzina rozpoczęcia** wybierz lub wprowadź godzinę rozpoczęcia cyklu.
1. Wykonaj jeden z następujących kroków:

    - Wybierz opcję **Brak daty zakończenia**, jeśli cykl nie powinien się kończyć.
    - Wybierz opcję **Zakończ po**, jeśli cykl ma kończyć się po pewnej liczbie uruchomień. W przypadku wybrania tej opcji należy wprowadzić liczbę uruchomień.
    - Wybierz opcję **Data zakończenia**, jeśli cykl nie powinien się kończyć w konkretnej dacie. Jeśli wybierzesz tę opcję, wybierz lub wprowadź datę.

1. Kliknij przycisk **OK**.
1. Kliknij przycisk **OK**.

## <a name="warranty-policies"></a>Zasady gwarancji

Po sprzedaniu przedłużonej gwarancji automatycznie jest tworzona jednostka zasad gwarancji. Numery polis gwarancyjnych mogą być współużytkowane z odbiorcami w taki sposób, aby zawierały odniesienie do zakupionych przez nich pozycji gwarancji. Do właściwości polis gwarancyjnych zalicza się datę rozpoczęcia obowiązywania oraz datę ważności gwarancji, warunków i postanowień oraz numer seryjny pozycji objętej gwarancją.

> [!NOTE]
> Podczas tworzenia jednostek zasad gwarancji automatycznie generowane są właściwości zasad dotyczących gwarancji. Obecnie nie można ich ręcznie konfigurować ani edytować.

W poniższej tabeli opisano właściwości zasad gwarancji oraz ich wartości. W Commerce Headquarters tabela bazy danych ma nazwę WARRANTYPOLICY.

| Nazwa właściwości | Wartość | opis |
|---------------|-------|-------------|
| PolicyNumber | Ciąg znaków (maksymalnie 20 znaków) | Numer polisy gwarancyjnej |
| WarrantiedItemId | Ciąg znaków (maksymalnie 20 znaków) | Identyfikator pozycji objętej gwarancją |
| WarrantiedInventoryLotId | Ciąg znaków (maksymalnie 20 znaków) | Identyfikator partii zapasów pozycji objętej gwarancją |
| WarrantiedSerialNumber | Ciąg znaków (maksymalnie 20 znaków) | Numer seryjny pozycji objętej gwarancją |
| WarrantiedFulfilledDate | Data | Identyfikator daty realizacji pozycji objętej gwarancją |
| WarrantyItemId | Ciąg znaków (maksymalnie 20 znaków) | Identyfikator pozycji gwarancji |
| WarrantyInventoryLotId | Ciąg znaków (maksymalnie 20 znaków) | Identyfikator partii zapasów pozycji gwarancji |
| WarrantySalesDate | Data | Identyfikator daty sprzedaży pozycji gwarancji |
| WarrantyEffectiveDate | Data | Identyfikator daty wejścia w życie polisy gwarancyjnej |
| WarrantyExpirationDate | Data | Identyfikator daty wygaśnięcia polisy gwarancyjnej |
| CustAccount | Ciąg znaków (maksymalnie 20 znaków) | Numer konta klienta |
| Stan | **Utworzone**, **unieważnione**, **obowiązujące** lub **wygasłe** | Identyfikator stanu polisy gwarancyjnej |
| Notatki | Ciąg znaków (maksymalnie 255 znaków) | Uwagi dotyczące polisy gwarancyjnej (np. warunków i postanowień) |

## <a name="frequently-asked-questions-faq"></a>Często zadawane pytania (FAQ)

**Dlaczego nie widzę monitu gwarancyjnego w punkcie sprzedaży?**

Upewnij się, że pozycja gwarancji jest w asortymencie w kanale. Upewnij się również, że grupa gwarancyji jest skonfigurowana w taki sposób, aby obejmowała odpowiedni kanał.

**Kiedy próbuję dodać gwarancję do istniejącej transakcji i wprowadzić numer paragonu zamówienia odbiorcy, dlaczego nie widzę żadnych towarów w wierszach transakcji?**

Przychody można wyszukać tylko wtedy, gdy jest wykonywane zadanie ściągania (zadanie P) w celu przekazania przychodów do Commerce Headquarter. Aby uruchomić zadanie P, przejdź do **Retail i Commerce \> Retail i Commerce — składniki IT \> Harmonogram dystrybucji**, wybierz zadanie **P-0001**, a następnie wybierz **Uruchom teraz**.

**Dlaczego funkcja gwarancji dotyczy tylko produktów z zserializowanymi produktami?**

Gwarancja to usługa oferowana dla konkretnego, unikatowego produktu. W Dynamics 365 produkt może być jednoznacznie identyfikowany tylko za pomocą numeru seryjnego.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie produktów handlu detalicznego](set-up-retail-products.md)

[Konfigurowanie asortymentów](set-up-assortments.md)

[Omówienie sekwencji identyfikatorów](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)
