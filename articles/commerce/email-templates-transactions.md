---
title: Tworzenie szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych
description: W tym temacie opisano sposób tworzenia, przekazywania i konfigurowania szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 245ca998ef3e6d172df3525f06d7901f3f41b650
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000794"
---
# <a name="create-email-templates-for-transactional-events"></a>Tworzenie szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób tworzenia, przekazywania i konfigurowania szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Dynamics 365 Commerce to gotowe rozwiązanie służące do wysyłania wiadomości e-mail powiadamiających odbiorców przy użyciu alertów o zdarzeniach transakcyjnych (na przykład o złożeniu zamówienia, zamówieniu gotowym do pobrania lub wysłaniu zamówienia). W tym temacie opisano kroki tworzenia, przekazywania i konfigurowania szablonów wiadomości e-mail używanych do wysyłania transakcyjnych wiadomości e-mail.

## <a name="create-an-email-template"></a>Tworzenie szablonu wiadomości e-mail

Aby można było mapować określone zdarzenie transakcyjne na szablon wiadomości e-mail, należy utworzyć szablon.

Aby utworzyć szablon wiadomości e-mail, należy wykonać poniższe kroki.

1. W centrali Commerce przejdź do **Szablony wiadomości e-mail organizacji**, które są znajdują się w **Retail i Commerce \> Ustawienia centrali \> Szablony wiadomości e-mail organizacji** lub **Administrowanie organizacją \> Konfiguracja \> Szablony wiadomości e-mail organizacji**.
1. Wybierz pozycję **Nowy**.
1. W obszarze **Ogólne** ustaw następujące pola:

    - **Identyfikator wiadomości e-mail** — identyfikator wiadomości e-mail to unikatowy identyfikator szablonu. Jest to wartość wyświetlana po wybraniu szablonu do mapowania na zdarzenie.
    - **Opis wiadomości e-mail** — to pole opcjonalne umożliwia wprowadzenie opisu szablonu. Wprowadzona wartość jest wyświetlana tylko w module Commerce Headquarters.
    - **Nazwa nadawcy** — wprowadzona nazwa jest wyświetlana w polu „od” większości klientów poczty e-mail.
    - **Adres e-mail nadawcy** — umożliwia wprowadzenie adresu e-mail, który ma być używany dla wiadomości e-mail wysyłanych za pomocą tego szablonu.
    - **Domyślny kod języka** — to pole określa zlokalizowaną wersję wiadomości e-mail, która jest wysyłana domyślnie, jeśli żaden język nie jest dostarczany przez kanał, który wywołuje ten szablon.

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

| Nazwa symbolu zastępczego    | Wartość symbolu zastępczego                                                |
|---------------------|------------------------------------------------------------------|
| customername        | Nazwa odbiorcy, który złożył zamówienie.                   |
| salesid             | Identyfikator zamówienia powiązanego ze sprzedażą.                                       |
| deliveryaddress     | Adres dostawy wysłanych zamówień.                         |
| customeraddress     | Adres odbiorcy.                                     |
| deliverydate        | Data dostawy.                                               |
| shipdate            | Data wysyłki.                                                   |
| modeofdelivery      | Metoda dostawy zamówienia.                                  |
| opłaty             | Łączne opłaty za zamówienie.                                 |
| podatek                 | Łączny podatek za zamówienie.                                     |
| suma               | Łączna kwota zamówienia.                                  |
| ordernetamount      | Łączna kwota zamówienia pomniejszona o łączny podatek.             |
| rabat            | Łączny rabat dla zamówienia.                                |
| storename           | Nazwa sklepu, w którym złożono zamówienie.                |
| storeaddress        | Adres sklepu, w którym złożono zamówienie.                  |
| storeopenfrom       | Godzina otwarcia sklepu, w którym złożono zamówienie.             |
| storeopento         | Godzina zamknięcia sklepu, w którym złożono zamówienie.             |
| pickupstorename     | Nazwa sklepu, w którym zamówienie zostanie odebrane.         |
| pickupstoreaddress  | Adres sklepu, w którym zamówienie zostanie odebrane.      |
| pickupopenstorefrom | Godzina otwarcia sklepu, w którym zamówienie zostanie odebrane. |
| pickupopenstoreto   | Godzina zamknięcia sklepu, w którym zamówienie zostanie odebrane. |

### <a name="order-line-placeholders-sales-line-level"></a>Symbole zastępcze wierszy zamówienia (poziom wiersza sprzedaży)

Poniższe symbole zastępcze pobierają i pokazują dane poszczególnych produktów (wierszy) w zamówieniu sprzedaży.

| Nazwa symbolu zastępczego               | Wartość symbolu zastępczego |
|--------------------------------|-------------------|
| productid                      | Identyfikator produktu dla wiersza. |
| lineproductname                | Nazwa produktu. |
| lineproductdescription         | Opis produktu. |
| linequantity                   | Liczba jednostek zamówionych dla wiersza oraz jednostka miary (na przykład **sztuka** lub **para**). |
| lineunit                       | Jednostka miary dotycząca danego wiersza. |
| linequantity_withoutunit       | Liczba jednostek zamówionych dla wiersza bez jednostki miary. |
| linequantitypicked             | Jeśli używane jest zdarzenie **PickOrder**, liczba jednostek, które zostały pobrane. W przeciwnym razie wartość **0** (zero). |
| linequantitypicked_withoutunit | Jeśli używane jest zdarzenie **PickOrder**, liczba jednostek, które zostały pobrane, bez jednostki miary. W przeciwnym razie wartość **0** (zero). |
| linequantitypacked             | Jeśli używane są zdarzenia **PackOrder** i **Zamówienie gotowe do odbioru**, liczba jednostek, które zostały zapakowane. W przeciwnym razie wartość **0** (zero). |
| linequantitypacked_withoutuom  | Jeśli używane są zdarzenia **PackOrder** i **Zamówienie gotowe do odbioru**, liczba jednostek, które zostały zapakowane, bez jednostki miary. W przeciwnym razie wartość **0** (zero). |
| linequantityshipped            | Zawsze wartość **0**, z wyjątkiem przypadków użycia określonych zdarzeń, zgodnie z opisem w następnym wierszu. |
| linequantityshipped_withoutuom | Jeśli używane jest zdarzenie **ShipOrder**, liczba jednostek, które zostały pobrane, bez jednostki miary. W przeciwnym razie wartość **0** (zero). |
| lineprice                      | Cena pojedynczej jednostki. |
| linenetamount                  | Cena wiersza po zastosowaniu liczby jednostek i rabatu. |
| linediscount                   | Rabat dla pojedynczej jednostki. |
| lineshipdate                   | Data wysyłki dla wiersza. |
| linedeliverydate               | Data dostawy dla wiersza. |
| linedeliverymode               | Metoda dostawy dla wiersza. |
| linedeliveryaddress            | Adres dostawy dla wiersza. |
| giftcardnumber                 | Identyfikator karty upominkowej dla produktów typu „karta upominkowa”. |
| giftcardbalance                | Saldo karty upominkowej dla produktów typu „karta upominkowa”. |
| giftcardmessage                | Wiadomość dołączona do karty upominkowej dla produktów typu „karta upominkowa”. |
| giftcardpin                    | Osobisty identyfikator PIN karty upominkowej dla produktów typu „karta upominkowa”. (Ten symbol zastępczy jest charakterystyczny dla zewnętrznych kart upominkowych). |
| giftcardexpiration             | Data ważności karty upominkowej dla produktów typu „karta upominkowa”. (Ten symbol zastępczy jest charakterystyczny dla zewnętrznych kart upominkowych). |
| giftcardrecipientname          | Imię i nazwisko odbiorcy karty upominkowej dla produktów typu „karta upominkowa”. |
| giftcardbuyername              | Imię i nazwisko nabywcy karty upominkowej dla produktów typu „karta upominkowa”. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Format symboli zastępczych wiersza zamówienia w treści wiadomości e-mail

Podczas tworzenia kodu HTML dla poszczególnych wierszy zamówienia w treści wiadomości e-mail należy otoczyć powtarzający się blok kodu HTML i symbole zastępcze dla wierszy zawierających poniższe symbole zastępcze, które są umieszczane wewnątrz tagów komentarzy HTML.

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

- Identyfikatorem e-mail szablonu wiadomości e-mail musi być **emailRecpt**.
- Tekst paragonu jest wstawiany do wiadomości e-mail za pomocą symbolu zastępczego **%message%**. Aby zapewnić prawidłowe renderowanie treści paragony, należy otoczyć symbol zastępczy **%message%** tagami HTML **&lt;pre&gt;** i **&lt;/pre&gt;**.
- Podziały wierszy w kodzie HTML dla nagłówka i stopki wiadomości e-mail są konwertowane na tagi HTML **&lt;br /&gt;**, dzięki czemu treść paragonu jest poprawnie renderowana. Aby wyeliminować niepożądany pionowy wolny obszar w wiadomościach e-mail z paragonem, usuń podziały wierszy z dowolnego miejsca w kodzie HTML, gdzie odstęp pionowy nie jest wymagany.

Aby uzyskać więcej informacji o sposobie konfigurowania paragonów w wiadomościach e-mail, zobacz temat [Ustawianie paragonów w wiadomościach e-mail](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-email-receipts).

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

[Ustawianie paragonów w wiadomościach e-mail](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Wysyłanie paragonów pocztą e-mail z aplikacji Modern POS](email-receipts.md)
