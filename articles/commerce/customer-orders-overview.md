---
title: Zamówienia odbiorców w punkcie sprzedaży (POS)
description: Ten temat zawiera informacje dotyczące zamówień odbiorcy w punkcie sprzedaży (POS). Zamówienia odbiorców są również nazywane zamówieniami specjalnymi. Temat przedstawia powiązane parametry i przepływy transakcji.
author: josaw1
ms.date: 01/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: e495ac4f3cc55503cc8b15d4d4640d3468ab7cd2
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936737"
---
# <a name="customer-orders-in-point-of-sale-pos"></a>Zamówienia odbiorców w punkcie sprzedaży (POS)

[!include [banner](includes/banner.md)]

Ten temat zawiera informacje dotyczące tworzenia zamówień odbiorcy w punkcie sprzedaży (POS) i zarządzania nimi. Zamówienia odbiorców mogą być używane do przechwytywania sprzedaży, w których Shoppers mają zostać pobrane produkty w późniejszym terminie, pobierać produkty z innej lokalizacji lub mieć wysłane do nich towary. 

W świecie wielokanałowego handlu wielu sprzedawców udostępnia opcję składania zamówień przez odbiorców, inaczej zamówień specjalnych, które pomagają spełnić różne wymagania dotyczące produktów i realizacji dostaw. Poniżej przedstawiono niektóre typowe scenariusze:

- Klient chce, aby produkty zostały dostarczane pod określony adres w określonym dniu.
- Klient chce odebrać produkty ze sklepu lub lokalizacji innej niż ta, w której kupił produkty.
- Odbiorca w lokalizacji sklepu chce zamawiać produkty dzisiaj i pobierać je z tego samego miejsca przechowywania w późniejszym terminie.

Sprzedawcy detaliczni mogą wykorzystać również zamówienia odbiorców, aby minimalizować utraconą sprzedaż, jaką mogą powodować przestoje w zaopatrzeniu, ponieważ towar może być dostarczany lub odbierany w różnych miejscach i czasie.

## <a name="set-up-customer-orders"></a>Konfigurowanie zamówień odbiorców
Przed próbą użycia funkcji zamówienia odbiorcy w punkcie sprzedaży należy upewnić się, że wszystkie wymagane konfiguracje zostały zakończone w module Commerce Headquarter.

### <a name="configure-modes-of-delivery"></a>Konfigurowanie metod dostawy

Aby skorzystać z zamówień odbiorców, należy skonfigurować metody dostawy, które mogą być używane w kanale sklepu. Należy zdefiniować co najmniej jedną metodę dostawy, która może być używana, gdy wiersze zamówienia są wysyłane do odbiorcy z sklepu. Należy zdefiniować co najmniej jedną metodę odbioru, która może być używana, gdy wiersze zamówienia są odbierane w sklepie. Metody dostawy są definiowane na stronie **Metody dostawy** w module Commerce Headquarter. Aby uzyskać więcej informacji dotyczących konfigurowania metody dostawy, należy zapoznać się z tematem [Ustawianie metod dostawy](./configure-call-center-delivery.md#define-delivery-modes).

![Strona metod dostawy](media/customer-order-modes-of-delivery.png)


### <a name="set-up-fulfillment-groups"></a>Ustawianie grup realizacji

Niektóre sklepy lub lokalizacje magazynowe mogą nie być w stanie zrealizować zamówień odbiorcy. Konfigurując grupy realizacji, organizacja może określić, które sklepy i lokalizacje magazynowe będą widoczne jako opcje dla użytkowników tworzących zamówienia odbiorców w punkcie sprzedaży. Grupy realizacji są konfigurowane na stronie **Grupy realizacji**. Organizacje mogą utworzyć tyle grup realizacji, ile jest potrzebnych. Po zdefiniowaniu grupy realizacji, jest ona połączona z sklepem za pomocą przycisku wybierajac **Przypisanie grupy realizacji** na karcie **Konfiguracja** w okienku akcji na stronie **Sklepy**.

W programie Commerce w wersji 10.0.12 i nowszych organizacje mogą określać, czy kombinacje magazynu i magazynu/sklepu, które są zdefiniowane w grupach realizacji, mogą być używane do wysyłki, do odbioru lub do wysyłki i odbioru. Zapewnia to firmie dodatkową elastyczność w określaniu, które magazyny mogą zostać wybrane podczas tworzenia zamówienia klienta na towary do wysyłki, a które sklepy można wybrać podczas tworzenia zamówienia klienta na towary do odbioru. Aby skorzystać z tych opcji konfiguracji, należy włączyć możliwość określania lokalizacji, w której jest włączona funkcja **Możliwość określenia lokalizacji jako „Wysyłka” lub „Odbiór” włączonej w grupie Fulfillment**. Jeśli magazyn połączony z grupą realizacji nie jest sklepem, można go skonfigurować tylko jako lokalizację wysyłki. Nie można jej użyć, jeśli w punkcie sprzedaży skonfigurowano zamówienia z odbiorem.

![Strona grup realizacji](media/customer-order-fulfillment-group.png)

### <a name="configure-channel-settings"></a>Konfigurowanie ustawień kanału

Podczas pracy z zamówieniami klientów w punkcie sprzedaży należy wziąć pod uwagę niektóre ustawienia kanału sklepu. Te ustawienia znajdują się na stronie **Sklepy** w module Commerce Headquarter.

- **Magazyn** — To pole wskazuje magazyn, który będzie używany podczas zmniejszania zapasów na potrzeby zamówień typu „transakcje kasowe i przeniesienia” oraz „pobrania” klientów powiązanych z tym sklepem. Zgodnie z najlepszą praktyką zachęcamy do korzystania z unikalnych magazynów dla każdego kanału sklepu, aby zapobiec konfliktom z logiką biznesową w różnych sklepach.
- **Magazyn wysyłek** — To pole wskazuje magazyn, który będzie używany podczas zmniejszania zapasów na zamówienia klientów, które mają zostać wysłane z wybranego sklepu. Jeśli funkcja **Możliwość określania lokalizacji jako „Wysyłka” lub „Odbiór” włączona w grupie Realizacji** została włączona w danym środowisku, użytkownicy punktu dostępu mogą wybrać określony magazyn do wysyłki w programie POS, zamiast wybierać sklep do wysyłki. Dlatego, gdy ta funkcja jest włączona, magazyn wysyłkowy nie jest już używany, ponieważ użytkownik wybierze określony magazyn do wysłania zamówienia od momentu utworzenia zamówienia.
- **Przypisanie grupy realizacji** — wybranie tego przycisku (na karcie **Konfiguracja** w okienku akcji) umożliwia połączenie grup realizacji, do których są pokazywane opcje dotyczące lokalizacji pobrania lub pośrednicy dla wysyłki podczas tworzenia zamówień odbiorców w punkcie sprzedaży.
- **Użycie podatku według lokalizacji docelowej** — ta opcja wskazuje, czy adres wysyłkowy jest używany do określania grupy podatków stosowanej do wierszy zamówienia wysyłanych na adres odbiorcy.
- **Użycie podatku opartego na odbiorcy** — ta opcja wskazuje, czy grupa podatków zdefiniowana dla adresu odbiorcy jest używana do opodatkowania zamówień odbiorców tworzonych w sprzedaży w celu wysyłki w domu odbiorcy.

![Konfiguracja kanału magazynowania na stronie sklepy](media/customer-order-all-stores.png)

### <a name="set-up-customer-order-parameters"></a>Konfigurowanie parametrów zamówienia odbiorcy

Przed próbą utworzenia zamówień odbiorców w punkcie sprzedaży należy skonfigurować odpowiednie parametry w module Commerce Headquarter. Te parametry można znaleźć na karcie **zamówienia klienta** na stronie **parametrów Commerce**.

- **Domyślny typ zamówienia** — umożliwia określenie typu zamówienia przypisanego domyślnie do zamówień odbiorcy tworzonych w punkcie sprzedaży. Zamówienia odbiorców mogą być zamówieniami sprzedaży lub ofertami sprzedaży. Niezależnie od domyślnego typu zamówienia użytkownicy nadal mogą tworzyć zamówienia sprzedaży i zamówienia odbioru w punkcie sprzedaży.
- **Domyślne procent depozytu** — określ kwotę, jaką odbiorca musi wpłacić jako depozyt, zanim zamówienie zostanie potwierdzone. W zależności od swoich uprawnień w module Magazyny, pracownicy mogą zastąpić tę kwotę za pomocą operacji **Zastąpienia wpłaty** w punkcie sprzedaży, jeśli ta operacja jest skonfigurowana dla układu ekranu transakcji.
- **Metoda dostawy — odbiór** — umożliwia określenie metody dostawy, która powinna być zastosowana do wierszy zamówienia sprzedaży skonfigurowanych do pobrania w punkcie sprzedaży.
- **Tryb dostawy — wyniesienie** — umożliwia określenie metody dostawy, która powinna być zastosowana do wierszy zamówienia sprzedaży uznawanych za zamówienia do wyniesienia w przypadku utworzenia koszyka mieszanego, w którym niektóre wiersze będą pobierane lub wysyłane, a inne wiersze będą od razu odbierane przez odbiorcę.
- **Procent opłaty za anulowanie** — jeśli z tytułu anulowania zamówienia odbiorcy będzie naliczana opłata, należy podać kwotę tej opłaty.
- **Kod opłaty za anulowanie** — umożliwia określenie kodu opłaty za rozrachunki z odbiorcami, który ma być używany, gdy opłata za anulowanie jest stosowana do anulowanych zamówień odbiorców w punkcie sprzedaży. Kod opłaty definiuje logikę księgowania finansowego dla opłaty za anulowanie.
- **Kod opłaty transportowej** — jeśli w polu **Używania opcji zaawansowanego automatycznego pobierania opłat** wybrana jest opcja **Tak**, to ustawienie parametru nie ma znaczenia. Jeśli ta opcja ma wartość **Nie**, użytkownicy będą proszeni o ręczne wprowadzenie opłaty transportowej podczas tworzenia zamówień odbiorców w punkcie sprzedaży. Ten parametr służy do mapowania kodu opłaty za rozrachunki z odbiorcami, który będzie stosowany do zamówień w momencie, gdy użytkownicy wprowadzą opłatę transportową. Kod opłaty definiuje logikę księgowania finansowego dla opłaty transportowej.
- **Korzystanie z zaawansowanych opłat automatycznych** — tę opcję należy ustawiać na **Tak**, aby przy tworzeniu zamówień odbiorców w punkcie sprzedaży były obliczane automatyczne opłaty systemowe. Te opłaty automatyczne mogą być używane do obliczania opłat za wysyłkę lub innych opłat związanych z zamówieniem lub produktem. Aby uzyskać informacje dotyczące konfiguracji funkcji zaawansowanych opłat automatycznych i korzystania z nich, należy zapoznać się z [Wielokanałowe zaawansowane opłaty automatyczne](./omni-auto-charges.md).

![Karta zamówienia odbiorcy na stronie parametrów Commerce](media/customer-order-parameters.png)

### <a name="update-transaction-screen-layouts-in-pos"></a>Aktualizowanie układów ekranu transakcji w punkcie sprzedaży

Upewnij się, że [układ ekranu punktu sprzedaży](./pos-screen-layouts.md) jest skonfigurowany do obsługi tworzenia i zarządzania zamówieniami odbiorców oraz że skonfigurowano wszystkie wymagane operacje punktu sprzedaży. Poniżej przedstawiono niektóre operacje punktu sprzedaży, które są zalecane do prawidłowej obsługi tworzenia i zarządzania zamówieniami odbiorców:
- **Wyślij wszystkie produkty** — ta operacja służy do określenia, że wszystkie wiersze w koszyku będą wysyłane do miejsca docelowego.
- **Wyślij wybrane produkty** — ta operacja służy do określenia, że wszystkie wybrane w koszyku wiersze będą wysyłane do miejsca docelowego.
- **Odbiór wszystkich produktów** — ta operacja służy do określenia, że wszystkie wiersze w koszyku będą odebrane z wybranego miejsca.
- **Odbiór wybranych produktów** — ta operacja służy do określenia, że wybrane wiersze w koszyku będą odebrane z wybranego miejsca.
- **Wyniesienie wszystkich produktów** — ta operacja służy do określenia, że będą wszystkie wiersze w danym koszyku zostaną wyniesione. Jeśli ta operacja jest używana w punkcie sprzedaży, zamówienie odbiorcy zostanie przekonwertowane na transakcję kasową i przeniesienia.
- **Wyniesienie wybranych produktów** — ta operacja służy do określenia, że wybrane wiersze w koszyku będą wyniesione przez odbiorcę w momencie zakupu. Ta operacja jest przydatna tylko w scenariuszu realizacji [zamówienia hybrydowego](./hybrid-customer-orders.md).
- **Odwołanie zamówienia** — ta operacja służy do wyszukiwania i pobierania zamówień odbiorcy, dzięki czemu użytkownicy w punkcie sprzedaży mogą edytować, anulować lub wykonywać w razie potrzeby operacje związane z realizacją.
- **Zmiana metody dostawy** — ta operacja umożliwia szybką zmianę trybu dostawy dla wierszy, które zostały już skonfigurowane do wysyłki, bez konieczności przechodzenia przez przepływ „Wyślij wszystkie produkty” lub „Wyślij wybrane produkty”.
- **Zastąpienie depozytu** — tej operacji można użyć do zmiany kwoty wpłaty zapłaconej przez odbiorcę dla wybranego zamówienia odbiorcy.

![Operacje na ekranie transakcja w punkcie sprzedaży](media/customer-order-screen-layout.png)

## <a name="work-with-customer-orders-in-pos"></a>Praca z zamówieniami odbiorcy w punkcie sprzedaży

> [!NOTE]
> Funkcja rozpoznawania przychodów nie jest obecnie obsługiwana w kanałach Commerce (handel zagraniczny, POS, biuro obsługi). Elementy skonfigurowane z rozpoznawaniem przychodów nie powinny być dodawane do zamówień utworzonych w kanałach Commerce. 

### <a name="create-a-customer-order-for-products-that-will-be-shipped-to-the-customer"></a>Utwórz zamówienie odbiorcy dla produktów, które zostaną wysłane do odbiorcy

1. Na ekranie transakcja punktu sprzedaży dodaj odbiorcę do transakcji.
2. Dodaj produkty do koszyka.
3. Wybierz opcję **Wyślij wybrany** lub **Wyślij wszystko**, aby wysłać produkty na adres na koncie odbiorcy.
4. Wybierz opcję, dla której ma zostać utworzone zamówienie odbiorcy.
5. Potwierdź lub zmień lokalizację „wysyłki z”, potwierdź lub zmień adres wysyłkowy i wybierz metodę wysyłki.
6. Umożliwia wprowadzenie oczekiwanej daty wysyłki zamówienia odbiorcy.
7. Należy użyć funkcji płatności, aby zapłacić za wszelkie kwoty należne lub użyć operacji **Zastąpienia depozytu**, aby zmienić kwoty należne, a następnie zastosować płatność.
8. Jeśli pełna suma zamówienia nie została zaksięgowana, należy wprowadzić kartę kredytową, która zostanie obciążona kwotą na zamówieniu, gdy zostanie ono zafakturowane.

### <a name="create-a-customer-order-for-products-that-the-customer-will-pick-up"></a>Utwórz zamówienie odbiorcy dla produktów, które zostaną odebrane przez odbiorcę

1. Na ekranie transakcja punktu sprzedaży dodaj odbiorcę do transakcji.
2. Dodaj produkty do koszyka.
3. Wybierz opcję **Odbierz wybrane** lub **Odbierz wszystko**, aby zainicjować konfigurację odbioru zamówienia.
4. Umożliwia wybranie lokalizacji przechowywania, z której odbiorca będzie pobierał wybrane produkty.
5. Wybierz datę pobrania pozycji.
6. Należy użyć funkcji płatności, aby zapłacić za wszelkie kwoty należne lub użyć operacji **Zastąpienia depozytu**, aby zmienić kwoty należne, a następnie zastosować płatność.
7. Jeśli pełna suma zamówienia nie została zastosowana, określ, czy odbiorca ma udzielić płatności później (przy odbiorze), czy też karta kredytowa będzie teraz obciążona a następnie używana i przechwycona w momencie odbioru.

### <a name="edit-an-existing-customer-order"></a>Edytowanie istniejącego zamówienia odbiorcy

Zamówienia detaliczne utworzone w ramach kanału online lub sklepowego mogą zostać odwołane i edytowane w punkcie sprzedaży zgodnie, jeśli zajdzie taka potrzeba.

> [!IMPORTANT]
> Nie wszystkie zamówienia detaliczne można edytować za pomocą aplikacji POS. Zamówień tworzonych w kanale biura obsługi nie można edytować za pośrednictwem punktu sprzedaży, jeśli [Włącz kończenie zamówienia](./set-up-order-processing-options.md#enable-order-completion) jest włączone dla kanału biura obsługi. Aby zapewnić poprawne przetwarzanie płatności, zamówienia utworzone w kanale biura obsługi i korzystające z funkcji włączania zamówień muszą być edytowane za pośrednictwem aplikacji centrum obsługi w module Commerce Headquarter.

W wersji 10.0.17 i późniejszej użytkownicy mogą edytować uprawnione zamówienia za pomocą aplikacji punktu sprzedaży, nawet jeśli zamówienie jest częściowo zrealizowane. Jednak zamówienia, które są w pełni zafakturowane nadal nie mogą być edytowane za pośrednictwem punktu sprzedaży. Aby włączyć tę funkcję, należy włączyć opcję **Edytowanie częściowo spełnionych zamówień w punktach sprzedaży** w obszarze roboczym **Zarządzanie funkcjami**. Jeśli ta funkcja nie jest włączona lub jeśli używasz wersji 10.0.16 lub starszej, użytkownicy będą mogli edytować zamówienia klientów w punkcie sprzedaży tylko wtedy, gdy zamówienie jest w pełni otwarte. Ponadto, jeśli ta funkcja jest włączona, możesz ograniczyć sklepy, które mogą edytować częściowo zrealizowane zamówienia. Opcję wyłączenia tej funkcji dla określonych sklepów można skonfigurować w profilu **Funkcjonalność** na skróconej karcie **Ogólne**.


1. Wybierz **Odwołaj zamówienie**.
2. Skorzystaj z **Wyszukiwania**, aby wprowadzić filtry w celu znalezienia zamówienia, a następnie wybierz przycisk **Zastosuj**.
3. Wybierz zamówienie na liście wyników, a następnie wybierz opcję **Edytuj**. Jeśli przycisk **Edytuj** jest niedostępny, zamówienie znajduje się w stanie, w którym nie można go edytować.
4. W koszyku transakcji wprowadź niezbędne zmiany w zamówieniu odbiorcy. Niektóre zmiany mogą być zabronione podczas edycji.
5. Zakończ proces edycji, wybierając operację płatności.
6. Aby wyjść z procesu edycji bez zapisywania zmian, można skorzystać z operacji **Unieważnij transakcję**.



### <a name="cancel-a-customer-order"></a>Anulowanie zamówienia odbiorcy

1. Wybierz **Odwołaj zamówienie**.
2. Skorzystaj z **Wyszukiwania**, aby wprowadzić filtry w celu znalezienia zamówienia, a następnie wybierz przycisk **Zastosuj**.
3. Wybierz zamówienie na liście wyników, a następnie wybierz opcję **Anuluj**. Jeśli przycisk **Anuluj** jest niedostępny, zamówienie znajduje się w stanie, w którym nie można go już anulować.
4. Jeśli są skonfigurowane opłaty za anulowanie, należy je potwierdzić. Opłaty za anulowanie można skorygować, jeśli jest to wymagane. 
5. W koszyku transakcji zakończ proces anulowania, wybierając operację płatności. Jeśli środki depozytowe, które zostały zapłacone, przekroczą wysokość opłaty za anulowanie, mogą być należne płatności za zwrot.
6. Aby wyjść z procesu anulowania bez zapisywania zmian, można skorzystać z operacji **Unieważnij transakcję**.

## <a name="finalizing-the-customer-order-shipment-or-pickup-from-pos"></a>Finalizowanie wysyłki lub odbioru zamówienia odbiorcy z punktu sprzedaży

Po utworzeniu zamówienia towary zostaną pobrane przez odbiorcę z lokalizacji magazynu lub wysłane, w zależności od konfiguracji zamówienia. Aby uzyskać więcej informacji na temat tego procesu, zapoznaj się z dokumentacją [realizacji zamówienia w sklepie](./order-fulfillment-overview.md).

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Asynchroniczny przepływ transakcji w zamówieniach odbiorców

Zamówienia odbiorców mogą być tworzone w aplikacji punktu sprzedaży (POS) w trybie synchronicznym lub asynchronicznym. Jeśli wykryjesz problemy z wydajnością lub opóźnienia użytkowników podczas tworzenia zamówień odbiorców w punkcie sprzedaży, rozważ włączenie tworzenia zamówienia asynchronicznego.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Włączanie funkcji tworzenia zamówień odbiorców w trybie asynchronicznym

1. W module Commerce Headquarter, na stronie **Profile funkcji** wybierz profil funkcji odpowiadający sklepowi, który ma zostać skonfigurowany.
2. Na skróconej karcie **Ogólne** w opcji **Utwórz zamówienie odbiorcy w trybie asynchronicznym** ustaw wartość **Tak**.

Gdy opcja **Utwórz zamówienie odbiorcy w trybie asynchronicznym** jest ustawiona na **Tak**, zamówienia odbiorców są zawsze tworzone w trybie asynchronicznym, nawet jeśli jest dostępna usługa Retail Transaction Service (RTS). Jeśli ustawisz tę opcję na **Nie**, zamówienia odbiorców są zawsze tworzone w trybie synchronicznym przy użyciu usługi RTS. Jeśli zamówienia odbiorców są tworzone w trybie asynchronicznym, są one ściągane i tworzone jako transakcje detaliczne w programie Commerce Headquarters z poziomu zadań ściągania Commerce (P). Odnośne zamówienia sprzedaży dla transakcji detalicznych są tworzone podczas wykonywania operacji **Synchronizuj zamówienia** ręcznie lub w procesie wsadowym.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Hybrydowe zamówienia odbiorców](hybrid-customer-orders.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]