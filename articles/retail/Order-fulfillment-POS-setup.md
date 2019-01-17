---
title: "Konfigurowanie realizacji zamówienia dla sklepów"
description: "Ten temat zawiera omówienie sposobu konfiguracji realizacji zamówienia w sklepie."
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: c8c2e56a1f65d28991dca3e1da4159efe81f2bf3
ms.contentlocale: pl-pl
ms.lasthandoff: 01/04/2019

---


# <a name="set-up-order-fulfillment-for-stores"></a>Konfigurowanie realizacji zamówienia dla sklepów

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Przegląd

Wielu sprzedawców chciałoby zoptymalizować realizację zamówień, umożliwiając to sklepom. Realizacja zamówienia na poziomie sklepu może ułatwić ograniczenie powstania zbyt dużych zapasów w określonym sklepie lub może być wymagana z logistycznego punktu widzenia w przypadkach, gdy sklep dysponuje dodatkowym miejscem lub znajduje się z mniejszej odległości wysyłki do klienta. Aby spełnić to wymaganie w punkcie sprzedaży dostępna jest ujednolicona operacja realizacji zamówienia.

Zamówienia do realizacji w określonym sklepie mają wyznaczony magazyn sklepu w nagłówku lub wierszach zamówienia.

Operacja realizacji zamówienia w punkcie sprzedaży zapewnia jeden obszar roboczy w punkcie sprzedaży, którego można użyć do realizacji zamówień. Obejmie to wszystkie aspekty od przyjęcia zamówienia do oznaczenia go jako wysłane lub zainicjowania odbioru w sklepie.

## <a name="set-up-the-order-fulfillment-operation"></a>Konfigurowanie operacji realizacji zamówienia

Realizacja zamówienia, [Identyfikator operacji 928](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-operations), umożliwia uzyskanie dostępu do obszaru roboczego realizacji zamówienia w sklepie w punkcie sprzedaży.

Wykonaj czynności opisane w sekcji [Dodawanie operacji do siatki przycisków](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts), aby określić, których parametrów używać w celu wywołania realizacji zamówienia w punkcie sprzedaży. Domyślnie po określeniu operacji realizacji zamówienia wybierana jest opcja **Wszystkie zamówienia**. Po skonfigurowaniu z tym parametrem operacja wyświetli listę wszystkich wierszy zamówienia do realizacji w bieżącym magazynie. Dostępna jest także opcja **Zamówienia do wysłania**, którą można przypisać do przycisku i użyć, gdy użytkownika chce zobaczyć tylko zamówienia, które zostaną wysłane ze sklepu. I wreszcie dostępna jest opcja **Zamówienia do odebrania**. Po użyciu w punkcie sprzedaży powoduje wyświetlenie listy zamówień do odbioru w sklepie. Do różnych przycisków można przypisać różne parametry umożliwiające użytkownikowi wyświetlanie realizacji zamówienia na kilka sposobów.

### <a name="enable-users-to-access-order-fulfillment-at-the-point-of-sale"></a>Zapewnienie użytkownikom dostępu do realizacji zamówienia w punkcie sprzedaży

Operacja realizacji zamówienia nie ma własnych uprawnień od razu po zainstalowaniu, ale w przyszłości użytkownicy mogą wymagać uprawnienia **Zezwalaj na pobieranie zamówienia** w celu wywołania operacji z punktu sprzedaży.

Na poziomie sklepu dostępne jest ustawienie konfiguracji określające, czy wiersz zamówienia musi zostać zaakceptowany ręczne z punktu sprzedaży. Jeśli ta opcja konfiguracji nie jest ustawiona, wiersze zamówienia będą akceptowane domyślnie. Jeżeli ta opcja konfiguracji jest włączona, użytkownicy w punkcie sprzedaży będą musieli posiadać uprawnienie **Zezwalaj na akceptowanie zamówienia**, aby akceptować zamówienia w punkcie sprzedaży.

### <a name="enable-manual-order-acceptance"></a>Włączanie ręcznego akceptowania zamówień

Domyślnie wiersze zamówienia przypisane do sklepu są oznaczone jako **Zaakceptowane**. Oznacza to przyjęcie założenie, że zostaną zrealizowane z przypisanego magazynu i nie zostaną przypisane po raz kolejny. W niektórych przypadkach może być konieczne ręczne zaakceptowanie zamówień przez sprzedawców przed ich realizacją. Jeżeli na przykład w sklepie brakuje pracowników i nie mogą zrealizować zamówienia, menedżer sklepu zaakceptuje tylko taką liczbę zamówień, jaką jego zdaniem można prawidłowo przetworzyć w danym dniu. Do momentu zaakceptowania zamówienia może zostać przypisane przez zaplecze do innego sklepu. Dzięki temu akceptowanie zamówienie umożliwia także określenie, że zamówienie zostało potwierdzone przez sklep i zostanie zrealizowane.

Wiersze zamówienia do odbioru w sklepie są oznaczone jako **Oczekujące** i nie podlegają akceptacji.

Aby włączyć ręczne akceptowanie wierszy zamówienia, przejdź do okna **Handel detaliczny** \> **Kanały** \> **Sklepy sieci sprzedaży** \> **Wszystkie sklepy sieci sprzedaży**. Wybierz sklep i kliknij jego identyfikator, aby wyświetlić szczegóły. Kliknij przycisk **Edytuj**. Na karcie skróconej **Ogólne** znajdź nagłówek podrzędny **Realizacja zamówienia** i zmień ustawienie opcji **Akceptuj ręcznie** z **Nie** na **Tak**.

### <a name="enable-reject-order-line-capability"></a>Włączanie funkcji odrzucania wiersza zamówienia

Wiersze zamówienia można także odrzucić z punktu sprzedaży. Odrzucenie wiersza zamówienia oznacza, że nie zostanie ono zrealizowane w tym sklepie i wysłanie go do ponownego przypisania w innym sklepie lub magazynie. Uprawnienie do odrzucania wiersza zamówienia jest przyznawane za pomocą uprawnienia **Zezwalaj na odrzucenie zamówienia** w grupie uprawnień punktu sprzedaży związanej z pracownikiem. Podczas odrzucania wiersza sklepy mogą wymagać od pracowników podania przyczyny odrzucenia. Można to zrobić, używając kodów informacji typu **Działanie dotyczące kodu informacji** **Realizacja zamówienia** i przypisując kod informacji do parametru **Odrzuć wiersz zamówienia** w profilu funkcji skojarzonym z kanałem.

> [!NOTE]
> Do akcji **Odrzuć wiersz zamówienia** można przypisać tylko kody informacji typu **Działanie dotyczące kodu informacji** **Realizacja zamówienia**.

### <a name="synchronize-changes-to-the-channel-database"></a>Synchronizowanie zmian z bazą danych kanału

Po przypisaniu operacji do siatki przycisków, przypisaniu prawidłowych uprawnień i skonfigurowaniu kanału należy zsynchronizować zmiany z bazą danych kanału. W tym celu przejdź do okna **Handel detaliczny** \> **Składniki IT w handlu detalicznym** \> **Harmonogram dystrybucji**. Wybierz harmonogram „1090-Kasy”, aby zsynchronizować zmiany siatki przycisków, a następnie kliknij przycisk **Uruchom teraz**. Następie zsynchronizuj zmiany uprawnień, wybierając opcję "1060-Personel” i kliknij przycisk **Uruchom teraz**. Następie zsynchronizuj zmiany kanału, wybierając opcję "1070-Konfiguracja kanału” i kliknij przycisk **Uruchom teraz**. Na koniec zsynchronizuj nowo utworzony kod informacji przyczyny odrzucenia, wybierając opcję „1110-Konfiguracja globalna” i kliknij przycisk **Uruchom teraz**.

## <a name="use-order-fulfillment-at-the-point-of-sale"></a>Korzystanie z realizacji zamówienia w punkcie sprzedaży

Otwórz punkt sprzedaży i wybierz operację realizacji zamówienia. W zależności od sposobu konfiguracji, zostaną wyświetlone wszystkie wiersze, wiersze zamówienia do odbioru lub wiersze zamówienia do wysłania.

### <a name="order-fulfillment-view"></a>Widok realizacji zamówienia

Widok realizacji zamówienia zawiera wiersze zamówienia do realizacji w sklepie i obejmuje następujące kolumny:

- Numer zamówienia
- Numer produktu
- opis
- Ilość zamówiona
- Wymagana data dostawy
- Nazwa odbiorcy
- Stan realizacji

Dodatkowe informacje o określonym wierszu zamówienia można wyświetlić, wybierając wiersz zamówienia, a następnie otwierając menu wysuwane znajdujące się tuż pod załogowanym użytkownikiem/informacjami o zmianie widocznymi w nagłówku punktu sprzedaży. To menu zawiera 2 karty: jedną ze szczegółami wiersza i jedną ze szczegółami zamówienia. Karta szczegółów wiersza zawiera następujące informacje:

- Ilość zamówiona
- Ilość pozostała do wysłania/pobrania
- Ilość pobrana
- Ilość zapakowana
- Ilość zafakturowana (już pobrana lub wysłana)
- Metoda dostawy
- Adres dostawy

Menu wysuwane szczegółów także zawiera kartę udostępniającą dodatkowe szczegóły poziomu zamówienia, w tym:

- Nazwa odbiorcy
- Identyfikator odbiorcy
- Numer zamówienia
- Suma zamówienia
- Saldo zamówienia

W dolnej części widoku realizacji zamówienia znajduje się okienko akcji. Zawiera wszystkie akcje, jakie można wykonać w odniesieniu do wiersza zamówienia. Jeżeli akcja jest niedostępna z powodu stanu wiersza, nie można jej wykonać.

Domyślnie zamówienia będą miały stan **Zaakceptowane**. Stan zamówienia można wyświetlić jako kolumnę na liście wierszy zamówienia. Jeżeli skonfigurowano opcję **Akceptuj ręcznie** na poziomie kanału, wszystkie wiersze do wysłania będą widoczne jako **Oczekujące** i muszą zostać zaakceptowane przed zrealizowaniem. Zamówienia do odbioru w sklepie mają domyślnie stan **Oczekujące** i nie muszą być akceptowane.

### <a name="order-fulfillment-line-actions"></a>Akcje dotyczące wierszy realizacji zamówienia

- **Edytuj** — jeżeli zamówienie ma stan Oczekujące, można je edytować w punkcie sprzedaży. Zamówień, które zostały już częściowo pobrane, spakowane lub zafakturowane nie można edytować w widoku realizacji zamówienia.
- **Akceptuj** — jeżeli funkcja **Akceptuj ręcznie** jest skonfigurowana na poziomie kanału, zanim linie będą mogły przejść przez proces realizacji zamówienia należy je najpierw zaakceptować.
- **Pobierz** — opcja pobierania obsługuje kilka akcji. Po pierwsze akcja **Pobranie** umożliwia aktualizacje stanu wiersza zamówienia, aby inne sklepy nie próbowały pobrać tego samego wiersza. Następnie akcja **Drukuj listę pobrania** umożliwia wydrukowanie listy pobrania dla wybranego wiersza lub wierszy, a także aktualizuje ich stan na **Pobranie**. Formaty listy pobrania są kontrolowane w ramach formatów paragonów. Aby uzyskać więcej informacji o sposobie konfigurowania formatów paragonów, zobacz [Szablony paragonów i drukowanie](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing). I wreszcie akcja **Oznacz jako pobrane** oznacza, że linia została pobrana. Akcja **Oznacz jako pobrane** inicjuje odpowiednie transakcje zapasów w zapleczu. Akcje pobrania można wykonywać w tym samym czasie dla wielu wierszy zamówienia w różnych zamówieniach i dla wszystkich sposobów dostawy.
- **Odrzuć** — wiersze lub wiersze częściowe można odrzucić. Pozwala na to ich ponowne przypisanie z zaplecza do innego sklepu lub magazynu. Wiersze można odrzucić tylko wtedy, gdy nie zostały pobrane ani spakowane. Aby odrzucić wiersz, który został już pobrany lub spakowany, należy cofnąć jego pobranie lub spakowanie z zaplecza.
- **Pakowanie** — opcja pakowania obsługuje dwie akcje: **Drukuj dokument dostawy** umożliwia wydrukowanie dokumentu dostawy dla wybranych wierszy, a akcja **Oznacz jako spakowane** umożliwia oznaczenie wierszy jako spakowanych oraz oznaczenie jako dostarczonych w zapleczu. Jednocześnie można pakować tylko wiersze zamówienia należące do tego samego zamówienia i o tym samym sposobie dostawy. Formaty dokumentów dostawy są kontrolowane w ramach formatów paragonów. Aby uzyskać więcej informacji o sposobie konfigurowania formatów paragonów, zobacz [Szablony paragonów i drukowanie](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing).
- **Wyślij** — wykonanie akcji wysyłania spowoduje oznaczenie wybranych wierszy jako**Dostarczone** w zapleczu. Po całkowitym wysłaniu wiersza nie będzie on już wyświetlany w widoku realizacji zamówienia.
- **Pobranie** — wykonanie akcji pobrania powoduje dodanie wierszy do widoku transakcji w celu pobrania. Jeżeli w zamówieniu istnieją inne wiersze, które nie są aktualnie pobierane, zostaną dodane do widoku transakcji z ilością równą zero. Po całkowitym pobraniu wiersza nie będzie on już wyświetlany w widoku realizacji zamówienia.

### <a name="order-fulfillment-filtering"></a>Filtrowanie realizacji zamówienia

Realizacja zamówienia w punkcie sprzedaży obejmuje filtrowanie ułatwiające użytkownikowi znalezienie wymaganych elementów. Filtry można zmieniać w okienku akcji w dolnej części ekranu **Punkt sprzedaży**. Domyślnie stosowany jest filtr **Typ dostawy** w zależności od sposobu skonfigurowania operacji. Jeżeli operacja została skonfigurowana z parametrem **Wszystkie zamówienia**, ten filtr jest stosowany po uzyskaniu dostępu do realizacji zamówienia. To samo dotyczy parametrów **Odbiór w sklepie** i **Wyślij z magazynu**. Inne filtry, które można zastosować do widoku realizacji zamówienia to:

- Numer odbiorcy
- Nazwa odbiorcy
- Adres e-mail odbiorcy
- Numer zamówienia
- Metoda dostawy
- Numer potwierdzenia
- Identyfikator odwołania do kanału
- Identyfikator sklepu, z którego pochodzi produkt
- Stan wiersza
- Data utworzenia
- Data dostawy
- Data przyjęcia

