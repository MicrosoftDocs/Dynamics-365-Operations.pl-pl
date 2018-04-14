---
title: "Omówienie realizacji zamówienia w sklepie"
description: "Ten temat zawiera omówienie modułu realizacji zamówienia w sklepie."
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
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 1ac73b50c6051ba7d3b96ae49cb7e33cf436ba9e
ms.contentlocale: pl-pl
ms.lasthandoff: 03/08/2018

---

# <a name="store-order-fulfillment"></a>Realizacja zamówienia w sklepie

[!INCLUDE [banner](includes/banner.md)]

Wielu sprzedawców chciałoby zoptymalizować realizację zamówień, umożliwiając to sklepom. Realizacja zamówienia na poziomie sklepu może ułatwić ograniczenie powstania zbyt dużych zapasów w określonym sklepie lub może być wymagana z logistycznego punktu widzenia w przypadkach, gdy sklep dysponuje dodatkowym miejscem lub znajduje się z mniejszej odległości wysyłki do klienta. Aby spełnić to wymaganie w punkcie sprzedaży dostępna jest ujednolicona operacja realizacji zamówienia.

Zamówienia do realizacji w określonym sklepie mają wyznaczony magazyn sklepu w nagłówku lub wierszach zamówienia. 

Operacja realizacji zamówienia w punkcie sprzedaży zapewnia jeden obszar roboczy w punkcie sprzedaży, którego można użyć do realizacji zamówień. Obejmie to wszystkie aspekty od przyjęcia zamówienia do oznaczenia go jako wysłane lub zainicjowania odbioru w sklepie. 

## <a name="access-unified-order-fulfillment-in-the-point-of-sale"></a>Dostęp do ujednoliconej realizacji zamówienia w punkcie sprzedaży

Realizacja zamówienia, [Identyfikator operacji 928](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-operations), umożliwia uzyskanie dostępu do obszaru roboczego realizacji zamówienia w sklepie w punkcie sprzedaży. 

Operacja realizacji zamówienia nie ma własnych uprawnień od razu po zainstalowaniu, ale w przyszłości użytkownicy będą mogli użyć uprawnienia **Zezwalaj na pobieranie zamówienia** w celu wywołania operacji z punktu sprzedaży.

Na poziomie sklepu dostępne jest ustawienie konfiguracji określające, czy wiersz zamówienia musi zostać zaakceptowany ręczne z punktu sprzedaży. Jeśli ta opcja konfiguracji nie jest ustawiona, wiersze zamówienia będą akceptowane domyślnie. Jeżeli ta opcja konfiguracji jest włączona, użytkownicy w punkcie sprzedaży będą musieli wybrać uprawnienie **Zezwalaj na akceptowanie zamówienia**, aby akceptować zamówienia w punkcie sprzedaży.
Wiersze zamówienia można także odrzucić z punktu sprzedaży. Odrzucenie wiersza zamówienia oznacza, że nie zostanie ono zrealizowane w tym sklepie i wysłanie go do ponownego przypisania w innym sklepie lub magazynie. Uprawnienie do odrzucenia wiersza zamówienia jest przyznawane za pomocą uprawnienia **Zezwalaj na odrzucenie zamówienia**. 

## <a name="order-fulfillment-operation-parameters"></a>Parametry operacji realizacji zamówienia

Realizacja zamówienia zawiera dostępne po instalacji parametry które można zastosować do operacji po jej wywołaniu w punkcie sprzedaży. Gdy parametr **Wszystkie zamówienia** jest skonfigurowany, użycie operacji powoduje wyświetlenie wszystkich zamówień. Parametr **Zamówienia do wysłania** umożliwia wyświetlenie tylko zamówień, które muszą zostać wysłane ze sklepu, a parametr **Zamówienia do odebrania** umożliwia wyświetlenie zamówień, które zostaną odebrane w sklepie. 

## <a name="orders-for-fulfillment"></a>Zamówienia do realizacji

Operacja realizacji zamówienia umożliwia wyświetlenie tylko tych zamówień, które zostaną odebrane w bieżącym sklepie lub z niego wysłane. Użycie operacji realizacji zamówienia nie powoduje wyświetlenia zamówień dla innych sklepów. 

## <a name="line-selection"></a>Wybór wiersza

Wiersze można wybrać za pomocą funkcji **Wybierz** w okienku akcji. Gdy funkcja **Wybierz** jest włączona można wybrać do przetwarzania wiele wierszy. Zaznaczenie wierszy można usunąć, klikając ponownie ten sam wiersz. 

## <a name="line-details"></a>Szczegóły wiersza

Szczegóły wiersza można wyświetlić, używając menu wysuwanego szczegółów wiersza. Gdy to menu jest używane, dostępne są trzy karty zawierające dodatkowe informacje o wybranym wierszu. Pierwsza karta, **Szczegóły wiersza** przedstawia szczegółowe informacje dotyczące wiersza, takie jak zamówiona i pozostała ilość. Dostępne są dodatkowe szczegółowe informacje, takie jak odebrana, spakowana i zafakturowana ilość, a także sposób i adres dostawy. Karta **Szczegóły zamówienia** zawiera informacje o nagłówku zamówienia, w tym nazwisko klienta, identyfikator klienta, numer zamówienia, sumę zamówienia i saldo. Na karcie **Zapasy** są wyświetlane informacje dla wybranego wiersza: fizycznie dostępne zapasy, zarezerwowane zapasy i zamówione zapasy.

Jeżeli zaznaczono kilka wierszy menu wysuwane szczegółów wiersza zamówienia będzie wskazywać tylko, że zaznaczono kilka wierszy. Aby wyświetlić szczegóły dotyczące jednego wiersza, usuwaj zaznaczenie wierszy, dopóki nie pozostanie tylko jeden wiersz. 

## <a name="pending-order-lines"></a>Oczekujące wiersze zamówień

Ujednolicona realizacja zamówienia obejmuje możliwość ręcznego akceptowania zamówień. Domyślnie zamówienia do realizacji w sklepie są już zaakceptowane. Jeżeli jednak procesy biznesowe określają, że pracownik musi zaakceptować zamówienia na poziomie sklepu, można włączyć akceptację ręczną na poziomie sklepu detalicznego. Aby włączyć akceptację zamówień, przejdź do okna **Handel detaliczny** > **Kanały** > **Sklepy sieci sprzedaży** > **Wszystkie sklepy sieci sprzedaży**. Otwórz odpowiedni sklep i na karcie **Ogólne** znajdź nagłówek podrzędny **Realizacja zamówienia**. Nagłówek podrzędny zawiera opcję **Akceptuj ręcznie**, która domyślnie jest ustawiona na **Nie**. Ustawienie tej opcji na **Tak** i zsynchronizowanie zmian z bazą danych kanału umożliwia przejście wierszy zamówień przez proces akceptacji.

Pracownicy z uprawnienie **Zezwalaj na akceptowanie zamówienia** mogą otworzyć realizację zamówienia i zaznaczyć wiersze do zaakceptowania. Po zaakceptowaniu wierszy ich stan zmienia się z **Oczekujące** na **Zaakceptowane** i można kontynuować proces realizacji zamówienia. Gdy opcja **Akceptuj ręcznie** jest włączona zamówienia będą przetwarzane dopiero po ich zaakceptowaniu. 

Zamówienia do odbioru w sklepie nigdy nie mają stanu **Oczekujące**. Ma to na celu uniknięcie scenariusza, w którym klient przychodzi do sklepu i nie można przetworzyć wiersza zamówienia, ponieważ pracownik z odpowiednimi uprawnieniami jest niedostępny.

## <a name="accepted-order-lines"></a>Zaakceptowane wiersze zamówienia

Zamówienia o stanie wiersza **Zaakceptowane** mogą przejść przez pozostały proces realizacji zamówienia w punkcie sprzedaży. Po zaakceptowaniu zamówienia można wykonać pozostałe czynności dotyczące wiersza zamówienia. 

Przykładowo wiersz zaakceptowanego zamówienia można zaznaczyć, a następnie odebrać bezpośrednio bez pobierania i pakowania.

## <a name="line-actions"></a>Akcje dotyczące wiersza

### <a name="pick"></a>Pobierz

Kategoria akcji **Pobierz** ułatwia proces pobierania wierszy zamówień z półek. Akcję pobrania można wykonać tylko w wierszach zamówień, które zostały wcześniej zaakceptowane. 

**Akcja: Pobranie**

- Wynikowy stan punktu sprzedaży: Pobranie
- Wynikowy stan zaplecza: Bez zmian

Po zaakceptowaniu zamówienia można zaznaczyć wiersze i oznaczyć je jako **Pobranie**. Zaznaczenie wiersza jako **Pobranie** oznacza, że w wierszu jest już wykonywane pobieranie. Zapobiega to próbie pobrania tego samego wiersza zamówienia przez dwóch pracowników jednocześnie.  

**Akcja: Drukuj listę pobrania**

- Wynikowy stan: Pobranie
- Wynikowy stan zaplecza: Bez zmian

Listy pobrania można wydrukować w punkcie sprzedaży, aby ułatwić pracownikom wykonywanie procesu pobierania. Pracownik może mieć przy sobie wydrukowaną listę pobrania i ręcznie oznaczać produkty jako pobrane na liście podczas wykonywania pobierania. 

Format listy pobrania jest skonfigurowany w rozwiązaniu Dynamics 365 for Retail i dodawany do profilu paragonów. Aby uzyskać więcej informacji o konfigurowaniu profili paragonów, zobacz [Szablony paragonów i drukowanie](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing).

Jeżeli wiersze są zaznaczone, a dla tych wierszy drukowana jest lista pobrania, ich stan jest automatycznie aktualizowany na **Pobranie**. 

**Akcja: Oznacz jako pobrane**

- Stan wynikowy: Pobrane lub częściowo pobrane
- Stan wynikowy zaplecza: Pobrane lub częściowo pobrane

Po wykonaniu procesu fizycznego pobrania wiersze można oznaczyć jako **Pobrane**. Zaznaczenie wiersza i oznaczenie jako **Pobrane** powoduje wykonanie w czasie rzeczywistym wywołania aktualizacji wiersza zamówienia w rozwiązaniu Dynamics 365 for Retail. Po oznaczeniu wiersza jako **Pobrane** w punkcie sprzedaży stan w zapleczu jest także aktualizowany na**Pobrane**, a w transakcjach uwzględniany jest fakt zmniejszenia o określoną ilość.

W trakcie przetwarzania zamówień można przetworzyć częściowe ilości dla określonego wiersza. Po zaznaczeniu wiersza i wykonaniu akcji **Oznacz jako pobrane**, gdy ilość jest większa niż jeden, wyświetlany jest monit o podanie ilości. Pozostała ilość do pobrania jest uzupełniana automatycznie. W przypadku określenia ilości mniejszej niż pozostała stan wiersza zmienia się na **Częściowo pobrane**. Po zaktualizowaniu wiersza zamówienia w zapleczu będzie ono także odzwierciedlać stan częściowego pobrania, a ilość wprowadzona przez użytkownika zostanie użyta do aktualizacji zapasów. 

Jeśli wiersz zamówienia został pobrany przez pomyłkę, należy wykonać proces dotyczący wiersza zamówienia w zapleczu. Obecnie w punkcie sprzedaży nie jest obsługiwana akcja cofnięcia pobrania. 

Wiersze zamówienia z różnych zamówień można zaznaczyć i oznaczyć jako **Pobranie**, wydrukować na tej samej liście pobrania lub oznaczyć jako **Pobrane**. 

### <a name="pack"></a>Pakunek

Wiersze zamówienia można spakować w dowolnym momencie po zaakceptowaniu wiersza zamówienia. 

**Akcja: Drukuj dokument dostawy**

- Stan wynikowy: Spakowane lub częściowo spakowane
- Stan wynikowy zaplecza: Dostarczone lub częściowo dostarczone

Ta akcja spowoduje oznaczenie wierszy jako spakowanych lub częściowo spakowanych i wydrukowanie dokumentu dostawy. Dokument dostawy można wydrukować, aby zweryfikować produkty spakowane razem. Format dokumentu dostawy jest skonfigurowany w rozwiązaniu Dynamics 365 for Retail i dodawany do profilu paragonów. Aby uzyskać więcej informacji o konfigurowaniu profili paragonów, zobacz [Szablony paragonów i drukowanie](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing).

**Akcja: Oznacz jako spakowane**

- Stan wynikowy: Spakowane lub częściowo spakowane
- Stan wynikowy zaplecza: Dostarczone lub częściowo dostarczone

Akcja **Oznacz jako spakowane** umożliwia wskazanie, że wiersze są spakowane bez drukowania dokumentu dostawy. Wykonanie akcji**Drukuj dokument dostawy** i **Oznacz jako spakowane** powodują wykonanie transakcji dotyczących zapasów w zapleczu. Wiersze pakowania w punkcie sprzedaży spowodują wygenerowanie arkuszy kasowych dostawy w zapleczu. 

Jeżeli wiersz zamówienia został spakowany przez pomyłkę, należy skorygować arkusza kasowy dostawy w zapleczu. 

Jednocześnie można pakować tylko wiersze w tym samym zamówieniu i o tym samym sposobie dostawy.

Obecnie opcja umożliwiająca oznaczenie wiersze odbioru w sklepie jako **Spakowane** jest wyłączona. Ta funkcja zostanie dodana w przyszłej wersji. Proces tworzenia dokumentu dostawy zostanie ulepszony tak, aby obsługiwał dodawanie do procesu tworzenia dokumentu dostawy informacji o wysyłce firm zewnętrznych.

### <a name="pick-up"></a>Pobierz

Zamówienia do odbioru w sklepie można odebrać bezpośrednio po ich pobraniu w punkcie sprzedaży. Zamówienia odbierane w sklepie nie podlegają akceptacji. 

**Akcja: Odbiór**

- Stan wynikowy: Zafakturowane lub częściowo zafakturowane
- Stan wynikowy zaplecza: Zafakturowane lub częściowo zafakturowane

Jeżeli wiersz zostanie wybrany do odbioru z ujednoliconej realizacji zamówienia, całe zamówienie zostanie załadowane do punktu sprzedaży i zostanie oznaczona pełna ilość dla wybranego wiersza. Inne wiersze w zamówieniu są także ładowane do widoku transakcji punktu sprzedaży, ale ilość jest oznaczana jako zero. 

Po załadowaniu wierszy do odbioru do widoku transakcji transakcję można opłacić w standardowy sposób. 

Wiersze, które zostały całkowicie zafakturowane za pomocą pobrania nie będą już wyświetlane w ujednoliconym przetwarzaniu zamówienia. Wiersze, które zostały pobrane częściowo, będą nadal wyświetlane w ujednoliconej realizacji zamówienia, aż do pobrania w całości. 

Jeżeli wiersz został pobrany przez pomyłką, należy dokonać zwrotu, aby skorygować błąd.  

Jednocześnie można pobrać tylko wiersze w tym samym zamówieniu i o tym samym sposobie dostawy. 

### <a name="shipping"></a>Wysyłka

Wiersze zamówienia do wysłania ze sklepu można przetworzyć za pomocą ujednoliconej realizacji zamówienia, używając akcji **Wysyłka**. Jeżeli na poziomie kanału skonfigurowano ręczną akceptację wiersza zamówienia, przed wysłaniem należy zaakceptować zamówienia. Po zaakceptowaniu zamówienia, które ma stan **Oczekujące** lub inny można wysłać wiersze. 

**Akcja: Wysyłka**

- Stan wynikowy: Zafakturowane lub częściowo zafakturowane
- Stan wynikowy zaplecza: Zafakturowane lub częściowo zafakturowane

Wiersze wysłane z ujednoliconej realizacji zamówienia są fakturowane z zaplecza w podobny sposób, jeżeli zamówienie jest fakturowane bezpośrednio z zaplecza. Wiersze wysyłane z ujednoliconej realizacji zamówienia nie są ładowane do widoku transakcji, a w momencie wysyłania wierszy nie jest dokonywana płatność. 

Wiersze zamówienia, które zostały całkowicie wysłane, nie są już wyświetlane w ujednoliconej realizacji zamówienia. Wiersze wysłane częściowo będą nadal wyświetlane w ujednoliconej realizacji zamówienia, aż do wysłania w całości. 

Jednocześnie można wysłać tylko wiersze z tego samego zamówienia. Jeżeli wiersze z tego samego zamówienia mają różne sposoby dostawy, nadal można je wybrać do jednoczesnej wysyłki. 

### <a name="reject"></a>Odrzuć

Wiersze lub wiersze częściowe można odrzucić. Pozwala na to ich ponowne przypisanie z zaplecza do innego sklepu lub magazynu. Wiersze można odrzucić tylko wtedy, gdy nie zostały pobrane ani spakowane. Aby odrzucić wiersz, który został już pobrany lub spakowany, należy cofnąć jego pobranie lub spakowanie z zaplecza. 

**Akcja: Odrzuć**

- Stan wynikowy: Odrzucone
- Wynikowy stan zaplecza: Bez zmian 

Odrzucone wiersze zamówień można wyświetlić w obszarze roboczym **Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania**. Aby wyświetlić wszystkie odrzucone wiersze zamówień ze sklepów, wyczyść filtr osób. Kara **Wiersze odrzuconego zamówienia** w sekcji **Zamówienia i ulubione** zawierają szczegóły wiersza zamówienia. Ponadto kliknięcie przycisku **Wiersze odrzuconego zamówienia** w sekcji **Podsumowanie** umożliwia przejście do widoku zamówienia sprzedaży. Powoduje to wyświetlenie wszystkich zamówień, które mają co najmniej jeden odrzucony wiersz zamówienia. Jeżeli funkcja Rozproszone zarządzanie zamówieniami (DOM) jest włączona, te odrzucone zamówienia zostaną automatycznie przypisane ponownie do odpowiednich sklepów w celu realizacji. Te wiersze zamówienia można także przypisać ponownie ręcznie. W tym celu zaznacz wiersz, którego **Stan realizacji** to **Odrzucony** i zmień odpowiednio sklep/magazyn. Kliknij menu rozwijane **Aktualizuj wiersz** i kliknij pozycję **Resetuj stan realizacji**, aby zmienić stan realizacji z **Odrzucony** na **Zaakceptowany** lub **Oczekujący**, w zależności od konfiguracji realizacji zamówienia. Po zresetowaniu stanu realizacji pracownicy sklepu będą mogli wyświetlić wiersze zamówienia w punkcie sprzedaży.

## <a name="line-quantity-tracking"></a>Śledzenie ilości wiersza

Pojedynczy wiersz zamówienia o ilości większej niż jeden można przetworzyć z biegiem czasu, co spowoduje powstanie wielu stanów podrzędnych dla wierszy zamówienia. Jeżeli na przykład konstruktor realizuje projekt, który wymagał 500 desek, ale w czasie realizacji odbierze lub otrzyma tylko kilka, mogą występować ilości pobierane, pakowane i wysyłane w tym samym czasie. 

Po każdym zaznaczeniu wiersza ilość pozostała w wierszu będzie automatycznie uzupełniania w celu założenia, że pozostała ilość jest przetwarzana. Zgodnie z powyższym przykładem, jeżeli pobrano już 200 desek i wiersz desek zostanie zaznaczony do pobrania, pozostała ilość wynosząca 300 zostanie automatycznie uzupełniona w ilości. To samo dotyczy przypadku, gdy 200 desek zostało już zafakturowanych. W takim przypadku tylko pozostała ilość zostanie wypełniona automatycznie. 

Kontynuując powyższy przykład: jeżeli 200 desek zostanie oznaczonych jako spakowane i zostanie wybrana wysyłka, automatycznie zostanie wypełniona pełna ilość 500 sztuk. Jeżeli wysyłanych jest tylko 200 desek, system założy, że wysyłane są wcześniej zapakowane deski i zapakowana ilość zostanie zmniejszona. Jeżeli wysyłanych jest 201 desek, najpierw odejmowane są zapakowane deski, a pozostała jedna jest odejmowana od pozostałej ilości. 

## <a name="line-statuses"></a>Stany wiersza

Wiersze zamówienia w punkcie sprzedaży mają kilka stanów określających stan wiersza zamówienia. Stan w punkcie sprzedaży i zapleczu nie są zgodne we wszystkich przypadkach. Stan wiersza zamówienia można wyświetlić w punkcie sprzedaży, używając operacji realizacji zamówienia. W zapleczu wiersze zamówienia można wyświetlić ze szczegółów zamówienia. Dostęp do szczegółów zamówienia można uzyskać wybierając opcję **Handel detaliczny** > **Odbiorcy** > **Wszystkie zamówienia odbiorcy**. Wybierz opcję **Identyfikator zamówienia**, aby wyświetlić szczegóły zamówienia. W oknie szczegółów zamówienia wybierz kartę **Zamówienie sprzedaży**, a następnie wybierz opcję **Szczegółowy stan** w nagłówku podrzędnym**Widok**. 

**Oczekujące** — wiersze zamówienia, które zostały przypisane do sklepu, but ale nie zostały jeszcze zaakceptowane mają po wyświetleniu w punkcie sprzedaży stan **Oczekujące**. Wiersze oczekujące na zaakceptowanie w punkcie sprzedaży będą miały w zapleczu stan **Przetwarzanie zamówień**.

**Zaakceptowane** — wiersze zamówienia, które zostały zaakceptowane ręcznie lub automatycznie, po wyświetleniu w punkcie sprzedaży będą miały stan **Zaakceptowane**. Wiersze o stanie **Zaakceptowane** będą widoczne w zapleczu jako **Przetwarzanie zamówień**.

**Pobranie** — wiersze aktualnie pobierane na poziomie sklepu mają stan **Pobieranie**. Te same wiersze po wyświetleniu w zapleczu będą widoczne jako **Przetwarzanie zamówień**.

**Pobrane** i **Częściowo pobrane** — wiersze, które zostały pobrane lub częściowo pobrane w punkcie sprzedaży będą miały stan **Pobrane** lub **Częściowo pobrane**. Te same wiersze będą widoczne w zapleczu jako **Pobrane** lub **Częściowo pobrane**.

**Spakowane** i **Częściowo spakowane** — wiersze, które zostały spakowane lub częściowo spakowane w punkcie sprzedaży będą miały stan **Spakowane** lub **Częściowo spakowane**. Te same wiersze będą widoczne w zapleczu jako **Dostarczone** lub **Częściowo dostarczone**.

**Częściowo zafakturowane** — wiersze, które zostały częściowo pobrane lub wysłane będą miały w punkcie sprzedaży i zapleczu stan **Częściowo zafakturowane**.

**Zafakturowane** — wiersze, które zostały całkowicie zafakturowane w punkcie sprzedaży nie będą już wyświetlane do realizacji. Stan tych wierszy w zapleczu to **Zafakturowane**.

## <a name="order-fulfillment-filtering"></a>Filtrowanie realizacji zamówienia

Realizacja zamówienia w punkcie sprzedaży obejmuje filtrowanie ułatwiające użytkownikowi znalezienie wymaganych elementów. Filtry można zmieniać za pomocą okienka akcji w dolnej części ekranu **Punkt sprzedaży**. Domyślnie stosowany jest filtr **Typ dostawy** w zależności od sposobu skonfigurowania operacji. Jeżeli operacja została skonfigurowana z parametrem **Wszystkie zamówienia**, ten filtr jest stosowany po uzyskaniu dostępu do realizacji zamówienia. To samo dotyczy parametrów **Odbiór w sklepie** i **Wyślij z magazynu**. Inne filtry, które można zastosować do widoku realizacji zamówienia to:

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

