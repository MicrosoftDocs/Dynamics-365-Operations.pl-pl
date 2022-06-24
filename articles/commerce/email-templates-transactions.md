---
title: Tworzenie szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych
description: W tym artykule opisano sposób tworzenia, przekazywania i konfigurowania szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9a4d67d901608e210b4060a655ce39f0ea707a52
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910557"
---
# <a name="create-email-templates-for-transactional-events"></a>Tworzenie szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych

[!include [banner](includes/banner.md)]


W tym artykule opisano sposób tworzenia, przekazywania i konfigurowania szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych w rozwiązaniu Microsoft Dynamics 365 Commerce.

Aplikacja Dynamics 365 Commerce oferuje gotowe rozwiązanie służące do wysyłania wiadomości e-mail powiadamiających klientów o zdarzeniach transakcyjnych. Na przykład wiadomości e-mail mogą być wysyłane po złożeniu zamówienia albo przygotowania go do odbioru lub wysłania tego zamówienia. W tym artykule opisano kroki tworzenia, przekazywania i konfigurowania szablonów wiadomości e-mail używanych do wysyłania transakcyjnych wiadomości e-mail.

## <a name="notification-types"></a>Typy powiadomień

Powiadomienia można skonfigurować w taki sposób, aby informować klientów pocztą e-mail o zdarzeniach w ramach zamówienia i cyklu życia klienta. Aby skonfigurować powiadomienia, musisz zmapować szablon wiadomości e-mail na typ powiadomienia, tworząc profil powiadomień pocztą e-mail w aplikacji Commerce. Więcej informacji na temat sposobu konfigurowania profilów powiadomień e-mail jest dostępnych w temacie [Konfigurowanie profilu powiadomienia e-mail](email-notification-profiles.md).

Aplikacja Dynamics 365 Commerce obsługuje następujące typy powiadomień.

### <a name="order-created"></a>Zamówienie utworzone

Typ powiadomienia o *zamówieniu utworzonym* jest wyzwalany podczas tworzenia nowego zamówienia sprzedaży w programie Commerce Headquarters.

> [!NOTE]
> Typ powiadomienia o zamówieniu utworzonym nie jest wyzwalany dla transakcji kasowych i przeniesienia, które mają miejsce na terminalu punktu sprzedaży (POS). W takim przypadku zostanie wygenerowany paragon w wiadomości e-mail i/lub do wydrukowania. Aby uzyskać więcej informacji, zobacz temat [Wysyłanie paragonów w wiadomościach e-mail z nowoczesnego punktu sprzedaży (MPOS)](email-receipts.md).

### <a name="order-confirmed"></a>Zamówienie potwierdzone

Typ powiadomienia o *zamówieniu potwierdzonym* jest wyzwalany w momencie wygenerowania dokumentu potwierdzenia zamówienia dla zamówienia sprzedaży w programie Commerce Headquarters.

### <a name="picking-completed"></a>Pobieranie zakończone

Typ powiadomienia o *zakończeniu pobierania* jest wyzwalany, gdy lista pobrania dla zamówienia jest oznaczona jako zakończona w programie Commerce Headquarters.

> [!NOTE]
> Typ powiadomienia o zakończeniu pobierania nie jest wyzwalany, gdy pozycja jest oznaczona jako pobrana w terminalu w punkcie sprzedaży.

### <a name="packing-completed"></a>Pakowanie zakończone

Typ powiadomienia o *zakończeniu pakowania* jest wyzwalany, gdy dokument dostawy dla zamówienia jest generowany w programie Commerce Headquarters na terminalu w punkcie sprzedaży.

Typ powiadomienia o zakończeniu pakowania obsługuje następujące dodatkowe symbole zastępcze wiadomości e-mail, które ułatwiają obsługę funkcji „zamówienie gotowe do pobrania” oraz wyszukiwania zamówień z transakcyjnych wiadomości e-mail.

| Nazwa symbolu zastępczego    | Cel |
| ------------------- | ------- |
| `pickupstorename`     | Nazwa sklepu, w którym zamówienie jest dostępne do pobrania. |
| `pickupstoreaddress`  | Adres sklepu, w którym zamówienie jest dostępne do pobrania. |
| `pickupstoreopenfrom` | Godzina otwarcia sklepu pobrania. |
| `pickupstoreopento` | Godzina zamknięcia sklepu pobrania. |
| `pickupchannelid`     | Identyfikator kanału sklepu dla sklepu pobrania. |
| `packingslipid`      | Identyfikator dokumentu dostawy dla zamówienia, które zostanie pobrane. |
| `confirmationid`      | Identyfikator potwierdzenia zamówienia, które zostanie pobrane. (Ten identyfikator jest czasami nazywany identyfikatorem odwołania kanału). |

Aby uzyskać więcej informacji o funkcjach wyszukiwania zaewidencjonowania klienta i wyszukiwania zamówień, zobacz tematy [Konfigurowanie wykrywania i przekierowywania lokalizacji geograficznej](geo-detection-redirection.md) oraz [Włączanie wyszukiwania zamówień dla realizacji transakcji gościa](order-lookup-guest.md).

### <a name="order-ready-for-pickup"></a>Zamówienie gotowe do odbioru

Typ powiadomienia o *zamówieniu gotowym do odbioru* jest wyzwalany, gdy zamówienie jest oznaczone jako zapakowane, a tryb dostawy w co najmniej jednym wierszu zamówienia ustawiono na **Odbiór przez klienta**.

> [!NOTE]
> Typ powiadomienia o zamówieniu gotowym do odbioru został uznany za przestarzałe na korzyść typu powiadomienia o zakończeniu pakowania. Ten typ powiadomienia jest dostosowywany według trybu dostawy.

### <a name="order-shipped"></a>Zamówienie wysłane

Typ powiadomienia o *zamówieniu wysłanym* jest wyzwalany w przypadku zafakturowania zamówienia z trybem dostawy oznaczającym odbiór poza sklepem.

> [!NOTE]
> Typ powiadomienia o zamówieniu wysłanym do odbioru został uznany za przestarzałe na korzyść typu powiadomienia o zafakturowaniu zamówienia. Ten typ powiadomienia jest dostosowywany według trybu dostawy.

### <a name="order-invoiced"></a>Zamówienie zafakturowane

Typ powiadomienia o *zamówieniu zafakturowanym* jest wyzwalany, gdy zamówienie zostanie zafakturowane w punkcie sprzedaży lub w programie Commerce Headquarters.

### <a name="issue-gift-card"></a>Wystaw kartę upominkową

Typ powiadomienia o *wystawieniu karty upominkowej* jest wyzwalany, gdy zamówienie sprzedaży zawierające produkt typu „karta upominkowa” zostanie zafakturowane.

> [!NOTE]
> Wiadomość e-mail z powiadomieniem o wystawieniu karty upominkowej jest wysyłana do odbiorcy karty upominkowej. Adresat karty upominkowej jest określony w programie Commerce Headquarters w wierszu zamówienia sprzedaży, na karcie **Pakowanie** w obszarze **Szczegóły wiersza**. Można go określić ręcznie lub programowo.

Typ powiadomienia o wystawieniu karty upominkowej obsługuje następujące dodatkowe symbole zastępcze.

| Nazwa symbolu zastępczego      | Cel |
| --------------------- | ------- |
| `giftcardnumber`        | Identyfikator karty upominkowej dla produktów typu „karta upominkowa”. |
| `availablebalance` | Kwota pozostała na karcie upominkowej. |
| `giftcardmessage`       | Wiadomość dołączona do karty upominkowej dla produktów typu „karta upominkowa”. |
| `giftcardpin`         | Osobisty identyfikator PIN karty upominkowej dla produktów typu „karta upominkowa”. (Ten symbol zastępczy jest charakterystyczny dla zewnętrznych kart upominkowych). |
| `giftcardexpiration`    | Data ważności karty upominkowej dla produktów typu „karta upominkowa”. (Ten symbol zastępczy jest charakterystyczny dla zewnętrznych kart upominkowych). |
| `giftcardrecipientname` | Imię i nazwisko odbiorcy karty upominkowej dla produktów typu „karta upominkowa”. |
| `giftcardbuyername`     | Imię i nazwisko nabywcy karty upominkowej dla produktów typu „karta upominkowa”. |

Aby uzyskać więcej informacji o kartach upominkowych, zobacz tematy [Cyfrowe karty upominkowe w handlu elektronicznym](digital-gift-cards.md) i [Obsługa zewnętrznych kart upominkowych](dev-itpro/gift-card.md).

### <a name="order-cancellation"></a>Anulowanie zamówienia

Typ powiadomienia o *anulowaniu zamówienia* jest wyzwalany, gdy zamówienie zostanie anulowane w programie Commerce Headquarters.

### <a name="customer-created"></a>Odbiorca utworzony

Typ powiadomienia o *odbiorcy utworzonym* jest wyzwalany podczas tworzenia nowej encji klienta w programie Commerce Headquarters.

### <a name="b2b-prospect-approved"></a>Prospekt B2B został zatwierdzony

Typ powiadomienia *Prospekt B2B został zatwierdzony* jest wyzwalany, gdy wniosek o dołączeniu prospektu zostanie zatwierdzony w programie Commerce Headquarters. Aby uzyskać więcej informacji dotyczących sposobu zatwierdzania lub odrzucania prospektów B2B, zobacz temat [Konfigurowanie użytkownika administratora dla nowego partnera biznesowego](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

Typ powiadomienia o zatwierdzeniu prospektu B2B obsługuje następujące dodatkowe symbole zastępcze.

| Nazwa symbolu zastępczego | Cel                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`       | Imię prospektu B2B wprowadzone w zgłoszeniu. |
| `lastname`         | Nazwisko prospektu B2B wprowadzone w zgłoszeniu. |
| `company`          | Nazwa firmy kandydata wprowadzona w zgłoszeniu. |
| `email`            | Adres e-mail prospektu wprowadzony w zgłoszeniu.   |
| `zipcode`          | Kod pocztowy głównego adresu prospektu. |
| `comments`         | Komentarz wprowadzony w zgłoszeniu przez prospekt. |
| `storename`        | Nazwa kanału, w którym został utworzony prospekt. |
| `storeurl`         | Domyślnie puste. Aby używać tego symbolu zastępczego, należy utworzyć rozszerzenie niestandardowe. |

### <a name="b2b-prospect-rejected"></a>Prospekt B2B został odrzucony

Typ powiadomienia *Prospekt B2B został odrzucony* jest wyzwalany, gdy wniosek o dołączeniu prospektu zostanie odrzucony w programie Commerce Headquarters. Aby uzyskać więcej informacji dotyczących sposobu zatwierdzania lub odrzucania prospektów B2B, zobacz temat [Konfigurowanie użytkownika administratora dla nowego partnera biznesowego](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

Typ powiadomienia o odrzuceniu prospektu B2B obsługuje następujące dodatkowe symbole zastępcze.

| Nazwa symbolu zastępczego | Cel                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`        | Imię prospektu B2B wprowadzone w zgłoszeniu. |
| `lastname`         | Nazwisko prospektu B2B wprowadzone w zgłoszeniu. |
| `company`          | Nazwa firmy kandydata wprowadzona w zgłoszeniu. |

## <a name="create-an-email-template"></a>Tworzenie szablonu wiadomości e-mail

Aby można było mapować określone zdarzenie transakcyjne na szablon wiadomości e-mail, należy utworzyć szablon.

Aby utworzyć szablon wiadomości e-mail, należy wykonać poniższe kroki.

1. W centrali Commerce przejdź do **Retail i Commerce \> Ustawienia centrali \> Szablony wiadomości e-mail organizacji** lub **Administrowanie organizacją \> Konfiguracja \> Szablony wiadomości e-mail organizacji**.
1. Wybierz pozycję **Nowy**.
1. W obszarze **Ogólne** ustaw następujące pola:

    - **Identyfikator adresu e-mail** — identyfikator adresu e-mail jest unikatowym identyfikatorem szablonu. Jest to wartość wyświetlana po wybraniu szablonu do mapowania na zdarzenie.
    - **Opis wiadomości e-mail** — to pole opcjonalne umożliwia wprowadzenie opisu szablonu. Wprowadzona wartość jest wyświetlana tylko w module Commerce Headquarters.
    - **Nazwa nadawcy** — wprowadzona nazwa jest wyświetlana w polu „od” większości klientów poczty e-mail.
    - **Adres e-mail nadawcy** — umożliwia wprowadzenie adresu e-mail, który ma być używany dla wiadomości e-mail wysyłanych za pomocą tego szablonu.
    - **Domyślny kod języka** — to pole określa zlokalizowaną wersję wiadomości e-mail, która jest wysyłana domyślnie, jeśli kanał, który wywołuje ten szablon, nie określa języka.

1. W obszarze **Zawartość wiadomości e-mail** wybierz pozycję **Nowe**.
1. W polu **Język** wprowadź język szablonu wiadomości e-mail. Później można dodać więcej języków i zlokalizowanych szablonów.
1. W polu **Temat** wprowadź temat wiadomości e-mail, który powinien pojawić się w polu tematu tej wiadomości.
1. Wybierz pozycję **Edytuj**, aby przekazać szablon wiadomości e-mail.

## <a name="create-an-email-message-body-by-using-html"></a>Tworzenie treści wiadomości e-mail przy użyciu kodu HTML

Treść wiadomości e-mail składa się z kodu HTML. Można użyć dowolnego układu, stylów i znakowania, na które zezwala język HTML oraz wbudowane kaskadowe arkusze stylów (CSS). Można również korzystać z obrazów, jeśli są one obsługiwane w publicznie dostępnym punkcie końcowym Internetu. Aby dodać obraz, wprowadź adres URL obrazu w atrybucie **src** tagu HTML **&lt;img&gt;**.

> [!NOTE]
> Klienci poczty e-mail nakładają ograniczenia dotyczące układu i stylu, które mogą wymagać wprowadzenia korekt w kodzie HTML i arkuszach stylów CSS używanych w treści wiadomości. Zalecamy zapoznanie się z najważniejszymi wskazówkami dotyczącymi tworzenia kodu HTML, które będą obsługiwane przez najpopularniejszych klientów poczty e-mail.

## <a name="add-placeholders-to-the-email-message-body"></a>Dodawanie symboli zastępczych do treści wiadomości e-mail

Wiadomość e-mail może zawierać symbole zastępcze, które są zastępowane wartościami specyficznymi dla odbiorcy i dla transakcji podczas generowania wiadomości e-mail. Symbole zastępcze zawsze są otoczone znakami procentu (%) i są wstawiane bezpośrednio do dokumentu HTML.

Oto przykład.

```html
<p>
    Hello %customername%,<br />
    Order number %salesid%, can be picked up from the <b>%pickupstorename%</b> store.
</p>
```

### <a name="order-placeholders-sales-order-level"></a>Symbole zastępcze zamówienia (poziom zamówienia sprzedaży)

Poniższe symbole zastępcze pobierają i pokazują dane zdefiniowane na poziomie zamówienia sprzedaży (w przeciwieństwie do poziomu wiersza sprzedaży).

| Nazwa symbolu zastępczego     | Cel                                                      |
| -------------------- | ------------------------------------------------------------ |
| `customername`         | Nazwa odbiorcy, który złożył zamówienie.               |
| `customeraddress`      | Adres odbiorcy.                                 |
| `customeremailaddress` | Adres e-mail wprowadzony przez klienta podczas realizacji zamówienia.     |
| `salesid`              | Identyfikator zamówienia powiązanego ze sprzedażą.                                   |
| `orderconfirmationid`  | Identyfikator międzykanałowy, który został wygenerowany podczas tworzenia zamówienia.   |
| `channelid`            | Identyfikator kanału detalicznego lub internetowego, za pośrednictwem których złożono zamówienie. |
| `deliveryname`         | Nazwa, która jest określona dla adresu dostawy.         |
| `deliveryaddress`      | Adres dostawy wysłanych zamówień.                     |
| `deliverydate`         | Data dostawy.                                           |
| `shipdate`             | Data wysyłki.                                               |
| `modeofdelivery`       | Metoda dostawy zamówienia.                              |
| `ordernetamount`       | Łączna kwota zamówienia pomniejszona o łączny podatek.         |
| `discount`            | Łączny rabat dla zamówienia.                            |
| `charges`              | Łączne opłaty za zamówienie.                             |
| `tax`                  | Łączny podatek za zamówienie.                                 |
| `total`                | Łączna kwota zamówienia.                              |
| `storename`            | Nazwa sklepu, w którym złożono zamówienie.            |
| `storeaddress`         | Adres sklepu, w którym złożono zamówienie.              |
| `storeopenfrom`        | Godzina otwarcia sklepu, w którym złożono zamówienie.         |
| `storeopento`          | Godzina zamknięcia sklepu, w którym złożono zamówienie.         |
| `pickupstorename`      | Nazwa sklepu, w którym zamówienie zostanie odebrane.\*   |
| `pickupstoreaddress`   | Adres sklepu, w którym zamówienie zostanie odebrane.\* |
| `pickupopenstorefrom`  | Godzina otwarcia sklepu, w którym zamówienie zostanie odebrane.\* |
| `pickupopenstoreto`    | Godzina zamknięcia sklepu, w którym zamówienie zostanie odebrane.\* |
| `pickupchannelid`     | Identyfikator kanału sklepu, który jest określony dla trybu odbioru dostawy.\* |
| `packingslipid`        | Identyfikator dokumentu dostawy, który został wygenerowany podczas pakowania wierszy w zamówieniu.\* |

\* Te symbole zastępcze zwracają dane tylko wtedy, gdy są używane dla typu powiadomienia o **zamówieniu gotowym do odbioru**. 

### <a name="order-line-placeholders-sales-line-level"></a>Symbole zastępcze wierszy zamówienia (poziom wiersza sprzedaży)

Poniższe symbole zastępcze pobierają i pokazują dane poszczególnych produktów (wierszy) w zamówieniu sprzedaży.

| Nazwa symbolu zastępczego               | Cel |
|--------------------------------|-------------------|
| `productid`                      | <p>Identyfikator produktu. Ten identyfikator uwzględnia warianty.</p><p><strong>Uwaga:</strong> ten symbol zastępczy został uznany za przestarzały na rzecz elementu `lineproductrecid`.</p> |
| `lineproductrecid`               | Identyfikator produktu. Ten identyfikator uwzględnia warianty. Jednoznacznie identyfikuje element na poziomie wariantu. |
| `lineitemid`                     | Identyfikator produktu na poziomie produktu. (Ten identyfikator nie uwzględnia wariantów). |
| `lineproductvariantid`           | Identyfikator wariantu produktu. |
| `lineproductname`                | Nazwa produktu. |
| `lineproductdescription`         | Opis produktu. |
| `linequantity`                   | Liczba jednostek zamówionych dla wiersza oraz jednostka miary (na przykład **sztuka** lub **para**). |
| `lineunit`                       | Jednostka miary dotycząca danego wiersza. |
| `linequantity_withoutunit`       | Liczba jednostek zamówionych dla wiersza bez jednostki miary. |
| `linequantitypicked`             | Jeśli używane jest zdarzenie **PickOrder**, liczba jednostek, które zostały pobrane. W przeciwnym razie wartość **0** (zero). |
| `linequantitypicked_withoutunit` | Jeśli używane jest zdarzenie **PickOrder**, liczba jednostek, które zostały pobrane, bez jednostki miary. W przeciwnym razie wartość **0** (zero). |
| `linequantitypacked`             | Jeśli używane są zdarzenia **PackOrder** i **Zamówienie gotowe do odbioru**, liczba jednostek, które zostały zapakowane. W przeciwnym razie wartość **0** (zero). |
| `linequantitypacked_withoutuom`  | Jeśli używane są zdarzenia **PackOrder** i **Zamówienie gotowe do odbioru**, liczba jednostek, które zostały zapakowane, bez jednostki miary. W przeciwnym razie wartość **0** (zero). |
| `linequantityshipped`            | Zawsze wartość **0**, z wyjątkiem przypadków użycia określonych zdarzeń, zgodnie z opisem w następnym wierszu. |
| `linequantityshipped_withoutuom` | Jeśli używane jest zdarzenie **ShipOrder**, liczba jednostek, które zostały pobrane, bez jednostki miary. W przeciwnym razie wartość **0** (zero). |
| `lineprice`                      | Cena pojedynczej jednostki. |
| `linenetamount`                  | Cena wiersza po zastosowaniu liczby jednostek i rabatu. |
| `linediscount`                   | Rabat dla pojedynczej jednostki. |
| `lineshipdate`                   | Data wysyłki dla wiersza. |
| `linedeliverydate`               | Data dostawy dla wiersza. |
| `linedeliverymode`               | Metoda dostawy dla wiersza. |
| `linedeliveryaddress`            | Adres dostawy dla wiersza. |
| `linepickupdate`                 | Data odbioru określona przez klienta dla zamówień korzystających ze sposobu odbioru. |
| `linepickuptimeslot`             | Zakres dat odbioru określony przez klienta dla zamówień korzystających ze sposobu odbioru. |
| `giftcardnumber`                 | Identyfikator karty upominkowej dla produktów typu „karta upominkowa”. |
| `giftcardbalance`                | Saldo karty upominkowej dla produktów typu „karta upominkowa”. |
| `giftcardmessage`                | Wiadomość dołączona do karty upominkowej dla produktów typu „karta upominkowa”. |
| `giftcardpin`                    | Kod PIN karty upominkowej dla produktów typu „karta upominkowa”. (Ten symbol zastępczy jest charakterystyczny dla zewnętrznych kart upominkowych). |
| `giftcardexpiration`             | Data ważności karty upominkowej dla produktów typu „karta upominkowa”. (Ten symbol zastępczy jest charakterystyczny dla zewnętrznych kart upominkowych). |
| `giftcardrecipientname`          | Imię i nazwisko odbiorcy karty upominkowej dla produktów typu „karta upominkowa”. |
| `giftcardbuyername`              | Imię i nazwisko nabywcy karty upominkowej dla produktów typu „karta upominkowa”. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Format symboli zastępczych wiersza zamówienia w treści wiadomości e-mail

Podczas tworzenia kodu HTML dla poszczególnych wierszy zamówienia w treści wiadomości e-mail należy otoczyć powtarzający się blok kodu HTML i symbole zastępcze dla wierszy zawierających poniższe symbole zastępcze. Zauważ, że symbole zastępcze znajdują się wewnątrz tagów komentarzy HTML.

```html
<!--%tablebegin.salesline%-->

(Insert the repeating block of HTML and placeholders for individual lines here.)

<!--%tableend.salesline%-->
```

Oto przykład.

```HTML
<table>
    <tr>
        <td>Product name</td>
        <td>Quantity</td>
        <td>Price</td>
    </tr>
    <!--%tablebegin.salesline%-->
    <tr>
        <td>%lineproductname%</td>
        <td>%linequantity_withoutunit%</td>
        <td>%lineprice%</td>
    </tr>
    <!--%tableend.salesline%-->
</table>
```

## <a name="create-a-template-for-emailed-receipts"></a>Tworzenie szablonu dla paragonów w wiadomościach e-mail

Paragony można wysyłać pocztą e-mail do odbiorców, którzy dokonują zakupów w punkt sprzedaży detalicznej. Na ogół kroki prowadzące do utworzenia szablonu paragonów wysłanych w wiadomościach e-mail są takie same jak w przypadku tworzenia szablonów dla innych zdarzeń transakcyjnych. Wymagane są jednak następujące zmiany:

- Symbol zastępczy **%message%** służy do wstawiania tekstu paragonu w wiadomości e-mail. Aby zapewnić prawidłowe renderowanie treści paragony, należy otoczyć symbol zastępczy **%message%** tagami HTML **&lt;pre&gt;** i **&lt;/pre&gt;**.
- Symbol **%receiptid%** zastępczy może służyć do pokazywania kodu PIN lub kodu kreskowygo reprezentującego identyfikator paragonu. (Kody PIN i kody kreskowe są dynamicznie generowane i obsługiwane przez usługę firmy trzeciej) Aby uzyskać więcej informacji na temat sposobu pokazywania kodu PIN lub kodu kreskowych w paragonie w wiadomościach e-mail, zobacz temat [Dodawanie kodu lub kodu kreskowych do wiadomości e-mail o transakcjach i paragonach](add-qr-code-barcode-email.md)..

## <a name="upload-the-email-html"></a>Przekazywanie kodu wiadomości e-mail

Po utworzeniu i przetestowaniu kodu HTML dla treści wiadomości należy go przekazać do modułu Commerce Headquarters. Obecnie nie można eksportować kodu HTML wiadomości e-mail. Dlatego należy obsługiwać główną kopię kodu HTML poza modułem Commerce Headquarters.

Aby przekazać nowy lub edytowany kod HTML szablonu wiadomości e-mail, wykonaj poniższe kroki.

1. W module Commerce Headquarters przejdź do pozycji **Retail i Commerce \> Ustawienia centrali \> Szablony wiadomości e-mail organizacji**.
1. Wybierz wiersz dla języka, dla którego chcesz dodać lub zamienić kod HTML. Można też wybrać opcję **Nowy**, aby utworzyć wiersz dla nowego języka.
1. Wybierz opcję **Edycja**.
1. W wyświetlonym oknie dialogowym wybierz pozycję **Przeglądaj**. Przejdź do dokumentu HTML, który chcesz przekazać, wybierz go, a następnie wybierz pozycję **Otwórz**.
1. Wybierz pozycję **Przekaż**.
1. Po wyświetleniu w oknie podglądu wiadomości e-mail w formacie HTML wybierz przycisk **OK**.
1. Upewnij się, że zostało zaznaczone pole wyboru **Ma treść** dla wiersza.

Jeśli moduł Commerce Headquarters został już skonfigurowany do wysyłania wiadomości e-mail, nowa lub zaktualizowana wiadomość e-mail zostanie wysłana do wszystkich odbiorców, którzy wykonują transakcję wywołującą zdarzenie mapowane na szablon.

Aby uzyskać więcej informacji o sposobie konfigurowania wiadomości e-mail w aplikacji Dynamics 365 Commerce, zobacz temat [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md).

## <a name="additional-resources"></a>Dodatkowe zasoby 

[Konfigurowanie profilu powiadomienia](email-notification-profiles.md)

[Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md)

[Ustawianie paragonów w wiadomościach e-mail](/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Wysyłanie paragonów pocztą e-mail z aplikacji Modern POS](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
