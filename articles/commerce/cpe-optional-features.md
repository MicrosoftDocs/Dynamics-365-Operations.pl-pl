---
title: Konfigurowanie opcjonalnych funkcji środowiska oceny usługi Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania funkcji opcjonalnych środowiska oceny Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6f7ba7e6de3791720458b509059f008423c73a82
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599827"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a>Konfigurowanie opcjonalnych funkcji środowiska oceny usługi Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania funkcji opcjonalnych środowiska oceny Microsoft Dynamics 365 Commerce.

## <a name="prerequisites"></a>Wymagania wstępne

Jeśli chcesz ocenić funkcje transakcyjnej poczty e-mail, muszą być spełnione następujące wymagania wstępne:

- Jest dostępny serwer poczty e-mail (serwer Simple Mail Transfer Protocol \[SMTP\]), który może być używany z poziomu subskrypcji platformy Microsoft Azure, w której jest inicjowane środowisko oceny.
- Masz dostęp do w pełni kwalifikowanej nazwy (FQDN)/adresu IP serwera, numeru portu SMTP oraz szczegółów uwierzytelniania.

## <a name="configure-the-image-back-end"></a>Konfigurowanie zaplecza obrazu

### <a name="find-your-media-base-url"></a>Znajdowanie podstawowego adresu URL multimediów

> [!NOTE]
> Aby można było wykonać tę procedurę, należy wykonać kroki opisane w części [Konfigurowanie witryny w usłudze Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).

1. Zaloguj się do konstruktora witryny Commerce przy użyciu adresu URL zanotowanego podczas inicjowania usługi handlu elektronicznego w trakcie aprowizacji (zobacz [Inicjowanie usługi handlu elektronicznego](provisioning-guide.md#initialize-e-commerce)).
1. Otwórz witrynę **Fabrikam** .
1. W menu po lewej stronie wybierz pozycję **Biblioteka multimediów**.
1. Wybierz dowolny składnik majątku dla pojedynczego obrazu.
1. W inspektorze właściwości po prawej stronie znajdź właściwość **Publiczny adres URL**. Wartość to adres URL. Oto przykład:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.

1. Zastąp ostatni identyfikator w adresie URL (**MA1nQC** w poprzednim przykładzie) następującym ciągiem: **search?fileName=**. Oto przykładowy adres URL po wprowadzeniu tej zmiany:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    Ten adres URL jest podstawowym adresem URL obiektu multimedialnego. Zanotuj go.

### <a name="update-the-media-base-url"></a>Aktualizowanie podstawowego adresu URL obiektu multimedialnego

1. Zaloguj się do Commerce headquarters.
1. Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail i Commerce \> Ustawienia kanału \> Profile kanału**.
1. Wybierz opcję **Edycja**.
1. W obszarze **Właściwości profilu** zastąp wartość właściwości **Podstawowy adres URL serwera multimediów** utworzonym wcześniej podstawowym adresem URL obiektu multimedialnego.
1. Wybierz kanał o nazwie **scXXXXXXXXX**.
1. W obszarze **Właściwości profilu** wybierz opcję **Dodaj**.
1. Dla dodanej właściwości wybierz pozycję **Podstawowy adres URL serwera multimediów** jako klucz właściwości. Jako wartość właściwości wprowadź podstawowy adres URL obiektu multimedialnego, który został utworzony wcześniej.
1. Wybierz opcję **Zapisz**.

## <a name="configure-and-test-the-email-server"></a>Konfigurowanie i testowanie serwera poczty e-mail

> [!NOTE]
> Wprowadzony tutaj serwer SMTP lub usługa poczty e-mail musi być dostępna z poziomu subskrypcji platformy Azure używanej dla środowiska.

1. Zaloguj się do Commerce headquarters.
1. Korzystając z menu po lewej stronie, przejdź do **Moduły \> Retail and Commerce \> Ustawienia centrali \> Parametry \> Parametry poczty e-mail**.
1. Na karcie **Ustawienia SMTP** w polu **Serwer poczty wychodzącej** wprowadź nazwę FQDN lub adres IP serwera SMTP lub usługi poczty e-mail.
1. W polu **Numer portu SMTP** wprowadź numer portu. (Jeśli nie korzystasz z protokołu Secure Sockets Layer \[SSL\] domyślnym numerem portu jest **25**).
1. Jeśli wymagane jest uwierzytelnianie, wprowadź wartości w polach **Nazwa użytkownika** i **Hasło**.
1. Wybierz opcję **Zapisz**.
1. Wybierz pozycję **Odśwież**.
1. Na karcie **Testowa wiadomość e-mail** w polu **Dostawca poczty e-mail** wybierz pozycję **SMTP**.
1. W polu **Wyślij do** wprowadź adres e-mail, pod który powinna zostać dostarczona testowa wiadomość e-mail.
1. Wybierz pozycję **Wyślij testową wiadomość e-mail**.

## <a name="configure-email-templates"></a>Konfigurowanie szablonów poczty e-mail

Dla każdego zdarzenia transakcyjnego, w ramach którego chcesz wysyłać wiadomości e-mail, musisz zaktualizować szablon wiadomości e-mail za pomocą prawidłowego adresu e-mail nadawcy.

1. Zaloguj się do Commerce headquarters.
1. Korzystając z menu po lewej stronie, przejdź do **Moduły \> Retail and Commerce \> Ustawienia centrali \> Parametry \> Szablony wiadomości e-mail organizacji**.
1. Wybierz **Pokaż listę**.
1. Dla każdego szablonu na liście należy wykonać następujące kroki:

    1. W polu **Adres e-mail nadawcy** wprowadź adres e-mail dla nadawcy.
    1. Opcjonalnie: w polu **Nazwa nadawcy** wprowadź nazwę, która ma być używana jako nazwa nadawcy.

1. Wybierz opcję **Zapisz**.

## <a name="customize-email-templates"></a>Dostosowywanie szablonów wiadomości e-mail

Możesz dostosować szablony wiadomości e-mail, tak aby były używane różne obrazy. Możesz również zaktualizować linki w szablonach, tak aby przenosiły Cię do środowiska oceny. W poniższej procedurze opisano sposób pobierania szablonów domyślnych, dostosowywania ich i aktualizowania szablonów w systemie.

1. W przeglądarce internetowej pobierz [plik zip domyślnych szablonów wiadomości e-mail oceny aplikacji Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) na komputer lokalny. Ten plik zawiera następujące dokumenty HTML:

    - Szablon potwierdzenia zamówienia
    - Wystaw szablon karty upominkowej
    - Szablon nowego zamówienia
    - Zapakuj szablon zamówienia
    - Wybierz szablon zamówienia

1. Szablony dostosowuje się za pomocą edytora tekstów lub HTML. Zobacz listę [obsługiwanych tokenów](#supported-tokens-in-the-email-template) w dalszej części tego tematu.
1. Zaloguj się do aplikacji Commerce.
1. Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Administrowanie organizacją \> Ustawienia \> Szablony wiadomości e-mail organizacji**.
1. Aby wyświetlić wszystkie szablony, należy rozwinąć listę po lewej stronie.
1. Dla każdego szablonu, który chcesz dostosować, wykonaj następujące kroki:

    1. Wybierz szablon ma liście.
    1. W obszarze **Zawartość wiadomości e-mail** wybierz odpowiednią wersję językową na liście. (Domyślny język to **en-us**).
    1. W obszarze **Zawartość wiadomości e-mail** wybierz pozycję **Edytuj**. Zostanie wyświetlone okienko **Przekaż szablon wiadomości e-mail**.
    1. Wybierz pozycję **Przeglądaj** i znajdź plik HTML, który ma dostosowaną zawartość.
    1. Wybierz pozycję **Przekaż**. Szablon zostanie przekazany do systemu i zostanie wyświetlony podgląd.
    1. Kliknij przycisk **OK**.
    1. Opcjonalnie: dostosuj właściwość **Temat** szablonu.
    1. Wybierz opcję **Zapisz**.

### <a name="supported-tokens-in-the-email-template"></a>Obsługiwane tokeny w szablonie wiadomości e-mail

Podczas renderowania poczty e-mail te tokeny zostaną zastąpione rzeczywistymi wartościami, które dotyczą klienta i jego zamówienia.

#### <a name="sales-order"></a>Zamówienie sprzedaży

Poniższe tokeny mają zastosowanie do całego zamówienia sprzedaży.

| Nazwa tokena | Token  |
|-------------------|-------|
| Numer zamówienia      | %salesid% |
| Nazwa odbiorcy   | %customername% |
| Adres dostawy  | %deliveryaddress% |
| Adres do faktury   | %customeraddress% |
| Data zamówienia        | %shipdate% |
| Metoda dostawy     | %modeofdelivery% |
| Dyskonto          | %discount% |
| Podatek         | %tax% |
| Suma zamówienia       | %total% |

#### <a name="sales-line"></a>Wiersz sprzedaży

Dla każdego produktu w zamówieniu następujące tokeny są wypełniane wartościami.

> [!NOTE]
> Umieść token **Lista produktów — początek** na początku bloku kodu HTML, który jest powtarzany dla każdego produktu, a token **Lista produktów — koniec** na końcu bloku.

| Nazwa tokena      | Token |
|------------------------|-------|
| Lista produktów - start   | \<!--%tablebegin.salesline% --\> |
| Lista produktów - koniec     | \<!--%tableend.salesline%--\> |
| Nazwa produktu           | %lineproductname% |
| opis            | %lineproductdescription% |
| Ilość               | %linequantity% |
| Cena wiersza jednostki        | %lineprice% (sprawdź) |
| Wszystkie pozycje w wierszu        | %linenetamount% |
| rabat wiersza          | %linediscount% |
| Data wysyłki              | %lineshipdate% |
| Metoda zaopatrzenia     | %linedeliverymode% |
| adres dostawy       | %linedeliveryaddress% |
| Jednostka sprzedaży dla wiersza | %lineunit% |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie środowiska oceny usługi Dynamics 365 Commerce](cpe-overview.md)

[Ustanowienie środowiska oceny Dynamics 365 Commerce](provisioning-guide.md)

[Konfigurowanie środowiska oceny usługi Dynamics 365 Commerce](cpe-post-provisioning.md)

[Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce](cpe-bopis.md)

[Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
