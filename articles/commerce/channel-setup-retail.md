---
title: Konfigurowanie kanału sprzedaży
description: W tym temacie opisano, jak dodać utworzyć nowy kanał sprzedaży w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8ac01f36912fa5e8a09bb4f324ef272cec737aa1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002388"
---
# <a name="set-up-a-retail-channel"></a>Konfigurowanie kanału sprzedaży


[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać utworzyć nowy kanał sprzedaży w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł Dynamics 365 Commerce obsługuje wiele kanałów sprzedaży detalicznej. Te kanały sprzedaży detalicznej obejmują sklepy internetowe, internetowe serwisy sprzedażowe i sklepy sieci sprzedaży (nazywane także sklepami tradycyjnymi). Każdy kanał sklepu detalicznego ma własne metody płatności, grupy cenowe, kasy punktów sprzedaży, konta przychodów i wydatków oraz personel. Wszystkie te elementy kanału sklepu detalicznego należy skonfigurować przed jego utworzeniem. 

Przed utworzeniem kanału sprzedaży należy przestrzegać [wymagań wstępnych dotyczących kanału](channels-prerequisites.md).

## <a name="create-and-configure-a-new-retail-channel"></a>Utwórz i skonfiguruj nowy kanał sprzedaży

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Kanały  \> Sklepy \> Wszystkie sklepy**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa** wprowadź nazwę nowego kanału.
1. W polu **Numer sklepu** wprowadź indywidualny numer sklepu. Liczba może być alfanumeryczna z maksymalną 10 znakami.
1. Na liście rozwijanej **Firma** wprowadź odpowiednią firmę.
1. Z listy rozwijanej **Magazyn** wybierz odpowiedni magazyn.
1. W polu **Strefa czasowa sklepu** wybierz odpowiednią strefę czasową.
1. Z listy rozwijanej **Grupa podatków** wybierz odpowiednią grupę podatków dla sklepu.
1. W polu **Waluta** wybierz odpowiednią walutę.
1. W polu **Książka adresowa klienta** podaj prawidłową książkę adresową.
1. W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę.
1. W polu **Profil funkcji** wybierz profil funkcji, jeśli ma to zastosowanie.
1. W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy rysunek przedstawia utworzenie nowego kanału sprzedaży.

![Nowy kanał sprzedaży](media/channel-setup-retail-1.png)

Poniższy obraz przedstawia przykład kanału sprzedaży.

![Przykład kanału sprzedaży](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Inne ustawienia

Istnieje wiele innych ustawień opcjonalnych, które można ustawiać w sekcjach **Zestawienie/zamknięcie** i **Różne**, na podstawie potrzeb sklepu detalicznego.

Ponadto zapoznaj się z tematami [Układy ekranu dla punktu sprzedaży (POS)](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json), aby uzyskać informacje dotyczące konfigurowania domyślnego układu ekranu w sekcji **Układ ekranu** oraz [Konfigurowanie i instalowanie modułu Retail Hardware Station](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation) z informacjami o konfiguracji w sekcji **Stacje sprzętowe**.

Poniższy obraz przedstawia przykład konfiguracji kanału sprzedaży.

![Przykład konfiguracji kanału sprzedaży](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>Konfiguracja kanałów dodatkowych

Istnieją dodatkowe pozycje, które należy skonfigurować dla kanału, które można znaleźć w **okienku akcji** w sekcji **Konfiguracja**.

Dodatkowe zadania wymagane do konfiguracji kanału online obejmują konfigurowanie metod płatności, deklaracji gotówki, metod dostawy, kont przychodów/wydatków, sekcji, przypisania grupy realizacji i sejfów.

Na poniższym rysunku przedstawiono różne dodatkowe opcje konfiguracji kanału sprzedaży detalicznej na karcie **Konfiguracja**.

![Konfigurowanie kanału](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a>Konfigurowanie metod płatności

Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W okienku nawigacji wybierz żądaną metodę płatności.
1. W sekcji **Ogólne** podaj **Nazwę operacji** i skonfiguruj inne żądane ustawienia.
1. Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład kart i metod płatności gotówką.

![Przykład metod płatności](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a>Ustawienia deklaracji gotówki

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Deklaracja gotówki**.
1. W okienku akcji wybierz opcję **Nowy**, a następnie Utwórz wszystkie zastosowane oznaczenia **Monety** i **Banknoty**.

Poniższy obraz przedstawia przykład kart i deklaracji gotówki.

![Ustawienia deklaracji gotówki](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Ustaw metody dostawy

Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w **okienku akcji**.  

Aby zmienić lub dodać metodę dostawy, wykonaj następujące kroki.

1. W okienku nawigacji przejdź do **Moduły \> Zarządzanie zapasami \> Metody dostawy**.
1. W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.
1. W sekcji **Kanały sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kanał. Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.

Poniższy obraz przedstawia przykład kart i metodę dostawy.

![Ustaw metody dostawy](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a>Konfiguruj konto wpływu/wpłaty lub wpływów/wydatków

Aby skonfigurować konto wpływów/wydatków, wykonaj następujące czynności.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Konto wpływów/wydatków**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa** wprowadź nazwę.
1. W polu **Wyszukaj nazwę** wprowadź wyszukiwaną nazwę.
1. Wprowadź typ konta w polu **Typ konta**.
1. Wprowadź tekst dla **Wiersza wiadomości 1**, **Wiersz wiadomości 2**, **Tekst dokumentu 1** i **Tekst dokumentu 2** w razie potrzeby.
1. W obszarze **Księgowanie** wprowadź informacje o księgowaniu.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład konta wpływów/wydatków.

![Konfiguruj konta wpływów/wydatków](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a>Konfigurowanie sekcji

Aby skonfigurować sekcje, wykonaj następujące czynności.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Sekcje**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W obszarze **Numer sekcji** wprowadź numer sekcji.
1. W polu **Opis** wprowadź opis.
1. W obszarze **Rozmiar sekcji** wprowadź rozmiar sekcji.
1. W razie potrzeby skonfiguruj dodatkowe ustawienia w **Ogólne** i **Statystka sprzedaży**.
1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-a-fulfillment-group-assignment"></a>Konfiguracja przypisania grupy realizacji

Aby skonfigurować przypisanie grupy realizacji, należy wykonać następujące czynności.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Przypisanie grupy realizacji**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Z listy rozwijanej **Grupa realizacji** wybierz grupę realizacja.
1. Z listy rozwijanej wybierz **Opis wprowadź** i wprowadź opis.
1. Na okienku akcji wybierz opcję **Zapisz**

Poniższy obraz przedstawia przykład konfiguracji przypisania grupy realizacji.

![Konfiguracja przypisań grupy realizacji](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Konfiguracja sejfów

Aby skonfigurować sejfy, wykonaj następujące czynności.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Sejfy**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Wprowadź nazwę sejfu.
1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)

[Konfigurowanie kanału internetowego](channel-setup-online.md)

[Konfigurowanie kanału biura obsługi](channel-setup-callcenter.md)

