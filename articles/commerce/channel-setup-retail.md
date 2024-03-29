---
title: Konfigurowanie kanału sprzedaży
description: W tym artykule opisano, jak dodać utworzyć nowy kanał sprzedaży w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 96723f24f879b38f0582f5f321e03624151117af
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276354"
---
# <a name="set-up-a-retail-channel"></a>Konfigurowanie kanału handlu detalicznego

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak dodać utworzyć nowy kanał sprzedaży w Microsoft Dynamics 365 Commerce.

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

![Nowy kanał sprzedaży.](media/channel-setup-retail-1.png)

Poniższy obraz przedstawia przykład kanału sprzedaży.

![Przykład kanału sprzedaży.](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Inne ustawienia

Istnieje wiele innych ustawień opcjonalnych, które można ustawiać w sekcjach **Zestawienie/zamknięcie** i **Różne**, na podstawie potrzeb sklepu detalicznego.

Ponadto zapoznaj się z tematami [Układy ekranu dla punktu sprzedaży (POS)](pos-screen-layouts.md), aby uzyskać informacje dotyczące konfigurowania domyślnego układu ekranu w sekcji **Układ ekranu** oraz [Konfigurowanie i instalowanie modułu Retail Hardware Station](retail-hardware-station-configuration-installation.md) z informacjami o konfiguracji w sekcji **Stacje sprzętowe**.

Poniższy obraz przedstawia przykład konfiguracji kanału sprzedaży.

![Przykład konfiguracji kanału sprzedaży.](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>Konfiguracja kanałów dodatkowych

Istnieją dodatkowe pozycje, które należy skonfigurować dla kanału, które można znaleźć w okienku akcji w sekcji **Konfiguracja**.

Dodatkowe zadania wymagane do konfiguracji kanału online obejmują konfigurowanie metod płatności, deklaracji gotówki, metod dostawy, kont przychodów/wydatków, sekcji, przypisania grupy realizacji i sejfów.

Na poniższym rysunku przedstawiono różne dodatkowe opcje konfiguracji kanału sprzedaży detalicznej na karcie **Konfiguracja**.

![Konfigurowanie kanału.](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a>Konfigurowanie metod płatności

Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W okienku nawigacji wybierz żądaną metodę płatności.
1. W sekcji **Ogólne** podaj **Nazwę operacji** i skonfiguruj inne żądane ustawienia.
1. Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład kart i metod płatności gotówką.

![Przykład metod płatności.](media/channel-setup-retail-5.png)

Poniższy obrazek pokazuje przykład metody płatności gotówką oraz konfigurację zakładki **Kwota**.

![Przykładowe ustawienie metody płatności dla kwot.](media/payment-methods-recount.png)

> [!NOTE]
> Wartości w zakładce **Kwota** są buforowane na serwerze detalicznym i nie będą obowiązywać natychmiast po uruchomieniu zadań harmonogramu dystrybucji. Może być konieczne ponowne uruchomienie Jednostka skalowania chmury, aby natychmiast zastosować te wartości do testów.

### <a name="set-up-cash-declaration"></a>Ustawienia deklaracji gotówki

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Deklaracja gotówki**.
1. W okienku akcji wybierz opcję **Nowy**, a następnie Utwórz wszystkie zastosowane oznaczenia **Monety** i **Banknoty**.

Poniższy obraz przedstawia przykład kart i deklaracji gotówki.

![Ustawienia deklaracji gotówki.](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Ustaw metody dostawy

Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w okienku akcji.  

Aby zmienić lub dodać metodę dostawy, wykonaj następujące kroki.

1. W okienku nawigacji przejdź do **Moduły \> Zarządzanie zapasami \> Metody dostawy**.
1. W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.
1. W sekcji **Kanały sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kanał. Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.

Poniższy obraz przedstawia przykład kart i metodę dostawy.

![Ustaw metody dostawy.](media/channel-setup-retail-7.png)

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

![Konfiguruj konta wpływów/wydatków.](media/channel-setup-retail-8.png)

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

![Konfiguracja przypisań grupy realizacji.](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Konfiguracja sejfów

Aby skonfigurować sejfy, wykonaj następujące czynności.

1. W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Sejfy**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Wprowadź nazwę sejfu.
1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="ensure-unique-transaction-ids"></a>Zapewnianie unikatowych identyfikatorów transakcji

W Commerce w wersji 10.0.18 identyfikatory transakcji wygenerowane dla punktu sprzedaży (POS) są sekwencyjne i zawierają następujące elementy:

- Stała część, która jest zlepkiem identyfikatora sklepu i identyfikatora terminalu. 
- Sekwencyjna część, która jest sekwencją numerów. 

Format to *{store}-{terminal}-{numbersequence}*. 

Ponieważ identyfikatory transakcji mogą być generowane w trybie offline i online, istnieją przypadki duplikowania identyfikatorów transakcji. Eliminacja duplikatów identyfikatorów transakcji wymaga ręcznego poprawiania danych. 

W Commerce w wersji 10.0.19 format identyfikatora transakcji został zaktualizowany w celu usunięcia sekwencyjnej części, a zamiast tego jest używany 13-cyfrowy numer wygenerowany przez obliczenie czasu w milisekundach od 1970 roku. Nowy numer identyfikatora transakcji po tej zmianie to *{store}-{terminal}-{millisecondsSince1970}*. Ta aktualizacja powoduje, że identyfikator transakcji nie jest sekwencyjny i że identyfikatory transakcji są zawsze unikatowe. 

> [!NOTE]
> Identyfikatory transakcji są przeznaczone tylko do użytku wewnętrznego, więc nie muszą być sekwencyjne. Jednak w wielu krajach identyfikatory paragonów muszą być sekwencyjne.

Nową funkcję formatu identyfikatora transakcji można włączyć w obszarze roboczym **Zarządzanie funkcjami**. 

Aby umożliwić używanie nowych identyfikatorów transakcji, należy wykonać następujące czynności:

1. W centrali Commerce wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.
1. Wyszukaj na liście moduł „Retail i Commerce”.
1. Wyszukaj nazwę funkcji **Włącz nowy identyfikator transakcji w celu uniknięcia duplikatów identyfikatorów transakcji**.
1. Wybierz funkcję, a następnie w prawym okienku naciśnij przycisk **Włącz teraz**.  
1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. Uruchom zadania **1070 Konfiguracja kanałów** i **1170 Rejestrator zadań punktu sprzedaży**, aby zsynchronizować włączone funkcje w sklepach.
1. Po wysłaniu zmian do sklepów terminale punktu sprzedaży muszą zostać zamknięte i ponownie otwarte, aby używać nowego formatu identyfikatora transakcji. 

> [!NOTE]
> Po włączeniu nowej funkcji formatu identyfikatora transakcji nie będzie można wyłączyć tej funkcji. Jeśli musi zostać wyłączona, skontaktuj się z pomocą techniczną Commerce.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne dotyczące konfiguracji kanału](channels-prerequisites.md)

[Konfigurowanie kanału internetowego](channel-setup-online.md)

[Konfigurowanie kanału biura obsługi](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
