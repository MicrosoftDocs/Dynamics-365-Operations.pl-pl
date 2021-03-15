---
title: Konfigurowanie kanałów biura obsługi
description: Ten temat zawiera informacje dotyczące sposobu przetwarzania zamówień dla biur obsługi przy użyciu modułu Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCROrderParameters, MCRSalesTableOrderHistory, SalesOrderProcessingWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: fde831bb08f45623f24805625f76c0a43460562a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985743"
---
# <a name="set-up-call-center-channels"></a>Konfigurowanie kanałów biura obsługi

[!include [banner](includes/banner.md)]

Firma można zdefiniować wiele kanałów biura obsługi w programie Dynamics 365 Commerce. Kanały biura obsługi konfiguruje się w oknie **Handel detaliczny i inny** \> **Kanały** \> **Biura obsługi** \> **Wszystkie biura obsługi** i są one specyficzne dla firmy.

Podczas tworzenia nowego kanału biura obsługi jest mu systemowo przypisywany numer jednostki operacyjnej. Ponieważ biura obsługi są tworzone jako jednostki operacyjne, użytkownicy mogą połączyć kanał biura obsługi z różnymi funkcjami aplikacji Commerce, takimi jak asortymenty, katalogi i określone metody dostawy.

Domyślny magazyn można skonfigurować w kanale biura obsługi. Następnie podczas tworzenia zamówień sprzedaży w tym kanale domyślny magazyn jest automatycznie wprowadzany w nagłówku zamówienia sprzedaży, chyba że inny magazyn został zdefiniowany dla odbiorcy wskazanego w zamówieniu sprzedaży. W takim wypadku domyślnie jest wprowadzany magazyn odbiorcy.

Aby korzystać z funkcji biura obsługi, użytkownicy muszą być połączeni z kanałem biura obsługi. Wszystkie zamówienia sprzedaży, które użytkownik tworzy w aplikacji Commerce, są automatycznie łączone z kanałem biura obsługi tego użytkownika. Obecnie jeden użytkownik nie może być połączony równocześnie z wieloma kanałami biura obsługi.

W kanale biura obsługi można również skonfigurować profil powiadamiania pocztą e-mail. Profil określa zestaw szablonów wiadomości e-mail, który jest używany podczas wysyłania wiadomości e-mail do odbiorców składających zamówienia za pośrednictwem kanału biura obsługi. Wyzwalacze wiadomości e-mail można skonfigurować dla zdarzeń systemowych, takich jak przesłanie zamówienia lub wysyła zamówionych towarów.

Aby można było poprawnie przetwarzać operacje sprzedaży za pośrednictwem kanału biura obsługi, należy zdefiniować dla kanału poprawne [metody płatności](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-payments) i metody dostawy.

Na poziomie kanału biura obsługi można określić inne wartości domyślne związane z wymiarami finansowymi, które będą łączone z zamówieniami tworzonymi w tym kanale.

## <a name="options-for-order-processing-behavior"></a>Opcje zachowań przetwarzania zamówień

Trzy ustawienia w konfiguracji biura obsługi mają znaczny wpływ na funkcje i narzędzia dostępne dla zamówień sprzedaży tworzonych przez biuro obsługi: **Włącz kończenie zamówienia**, **Włącz sprzedaż bezpośrednią** i **Włącz kontrolę ceny zamówienia**.

### <a name="enable-order-completion"></a>Włącz kończenie zamówienia

Ustawienie **Włącz kończenie zamówienia** w kanale biura obsługi ma znaczny wpływ na przebieg przetwarzania zamówień sprzedaży wprowadzanych w tym kanale. Gdy to ustawienie jest włączone, wszystkie zamówienia sprzedaży muszą przejść przez zestaw reguł sprawdzania poprawności, zanim będzie można je potwierdzić. Reguły te są uruchamiane poprzez naciśnięcie przycisku **Ukończ**, który jest dodawany w okienku akcji na stronie zamówienia sprzedaży. Wszystkie zamówienia sprzedaży, które są tworzone przy włączonym ustawieniu **Włącz kończenie zamówienia**, muszą przejść przez proces finalizowania zamówienia. Ten proces wymusza odczytanie logiki płatności i weryfikacji płatności. Proces przesyłania zamówień może nie tylko służyć egzekwowaniu płatności, ale również wywoływać [funkcje wykrywania oszustw](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts) skonfigurowane w systemie. Zamówienia, które nie przeszły weryfikacji płatności lub braku oszustwa, są wstrzymywane i nie mogą zostać zwolnione do dalszego przetwarzania (na przykład do pobrania lub wysyłki), dopóki problem powodujący wstrzymanie nie zostanie rozwiązany.

Gdy kanał biura obsługi ma włączone ustawienie **Włącz kończenie zamówienia**, to w sytuacji, gdy po wprowadzeniu pozycji wierszy w zamówieniu sprzedaży użytkownik kanału spróbuje zamknąć formularz zamówienia sprzedaży lub z niego wyjść bez uprzedniego naciśnięcia przycisku **Ukończ**, system wymusza proces finalizowania zamówienia, otwierając stronę podsumowania zamówienia sprzedaży i wymagając, aby użytkownik poprawnie przesłał zamówienie. Jeżeli zamówienia nie można poprawnie przesłać razem z płatnością, użytkownik może za pomocą funkcji [wstrzymań zamówień](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) wstrzymać zamówienie. Jeśli użytkownik próbuje anulować zamówienie, musi to zrobić poprawnie, używając funkcji Anuluj lub Usuń, w zależności od tego, na którą funkcję pozwalają ustawienia zabezpieczeń użytkownika.

Jeśli ustawienie **Włącz kończenie zamówienia** jest włączone dla kanału biura obsługi, pole **Stan płatności** będzie śledzone w zamówieniu. System oblicza wartość **Stan płatności** po przesłaniu zamówienia sprzedaży. Tylko zamówienia ze stanem płatności Zatwierdzone mogą przechodzić przez system do kolejnych etapów przetwarzania zamówienia, takich jak pobranie i wysyłka. Jeśli płatności zostaną odrzucone, w szczegółowym stanie zamówienia zostanie włączona flaga **Nie przetwarzaj**. Spowoduje to wstrzymanie zamówienia do czasu rozwiązania problemu z płatnościami.

Ponadto jeśli jest włączone ustawienie **Włącz kończenie zamówienia**, to gdy użytkownicy tworzą zamówienia sprzedaży w trybie wprowadzania pozycji w wierszu, w głównym nagłówku zamówienia sprzedaży będzie dostępne pole **Źródło**. Pole **Źródło** zawiera [kod źródłowy katalogu](https://docs.microsoft.com/dynamics365/unified-operations/retail/call-center-catalogs) w scenariuszach sprzedaży w marketingu bezpośrednim. Ten kod może następnie decydować o cenach specjalnych i promocjach.

Nawet jeśli ustawienie **Włącz kończenie zamówienia** jest wyłączone, użytkownicy nadal mogą zastosować kod źródłowy do zamówienia sprzedaży. Jednak najpierw muszą otworzyć szczegóły nagłówka zamówienia sprzedaży, aby uzyskać dostęp do pola **Źródło**. Innymi słowy wymagane są pewne dodatkowe kliknięcia. Takie samo zachowanie dotyczy funkcji takich jak finalizowanie wysyłki i zamówienia przyspieszone. Funkcje te są dostępne dla wszystkich zamówień tworzonych w biurze obsługi. Jednak gdy jest włączone ustawienie **Włącz kończenie zamówienia**, użytkownicy widzą konfigurację tych funkcji w nagłówku sprzedaży podczas pracy w widoku wprowadzania wierszy. Nie muszą przechodzić do szczegółów nagłówka zamówienia sprzedaży, aby znaleźć odpowiednie ustawienia i pola.

### <a name="enable-direct-selling"></a>Włącz sprzedaż bezpośrednią

Jeśli w kanale biura obsługi jest włączone ustawienie **Włącz sprzedaż bezpośrednią**, użytkownicy mogą korzystać z funkcji sprzedaży dodatkowej i wiązanej dostępnych w aplikacji Commerce. W takim przypadku podczas wprowadzania zamówień pojawiają się wyskakujące okienka z sugestiami innych produktów, które użytkownik biura obsługi może zaoferować odbiorcy. Propozycje produktów bazują na produkcie, który został właśnie zamówiony w wierszu zamówienia sprzedaży. Obecnie sugestie sprzedaży dodatkowej i wiązanej konfiguruje się na poziomie pozycji w produktach i katalogach. Jeśli ustawienie **Włącz sprzedaż bezpośrednią** jest wyłączone w kanale biura obsługi, wyskakujące okienka nie są wyświetlane podczas wprowadzania zamówień, nawet jeśli dla zamawianego towaru zdefiniowano prawidłowe możliwości sprzedaży dodatkowej lub wiązanej.

Gdy ustawienie **Włącz sprzedaż bezpośrednią** jest włączone, skrypty i funkcje obrazów na stronie wprowadzania zamówienia sprzedaży są również włączone. W takim przypadku podczas wprowadzania zamówień przy prawej krawędzi strony znajduje się panel informacji. Panel może pokazywać skrypty związane ze standardowym procesem wprowadzania zamówień, zastosowany kod źródłowy katalogu lub skrypty odnoszące się do zamawianych towarów. Ponadto panel obrazów może pokazywać obraz produktu dla zamawianych towarów, o ile obraz został zdefiniowany dla towaru w konfiguracji produktu.

### <a name="enable-order-price-control"></a>Włącz kontrolę ceny zamówienia

Gdy ustawienie **Włącz kontrolę ceny zamówienia** jest włączone, tylko autoryzowani użytkownicy mogą zmieniać cenę sprzedaży towaru podczas wprowadzania zamówień. Zmiany muszą być w granicach określonych tolerancji. Użytkownicy, którzy nie mają odpowiedniej autoryzacji, muszą zamiast tego przesłać wniosek o zmianę ceny. Wniosek będzie przetwarzany przy użyciu systemowych przepływów pracy weryfikacji i zatwierdzenia.

## <a name="channel-users"></a>Użytkownicy kanału

Po zdefiniowaniu kanału biura obsługi należy połączyć użytkowników kanału z biurem obsługi. W przeciwnym razie nie będzie można używać biura obsługi w systemie. Gdy użytkownik loguje się do aplikacji Commerce i wprowadza zamówienia sprzedaży lub zamówienia zwrotu na stronie związanej z wprowadzaniem zamówień, jego identyfikator użytkownika jest weryfikowany względem konfiguracji kanału biura obsługi. Jeśli użytkownik jest połączony z określonym kanałem biura obsługi, zamówienia tworzone przez tego użytkownika dziedziczą cechy i domyślne wartości tego kanału.

Domyślnie we wszystkich zamówieniach tworzonych przez użytkowników biura obsługi jest włączona flaga **Sprzedaż** w nagłówku zamówienia sprzedaży. Wtedy zamówienia mogą korzystać z systemowych funkcji cen i promocji specyficznych dla handlu.


Użytkownicy, którzy nie są połączeni z kanałem biura obsługi, używają standardowych funkcji wprowadzania zamówień zawartych w Microsoft Dynamics 365 Finance. Zamówienia wprowadzane przez tych użytkowników za pośrednictwem formularza wprowadzania zamówień sprzedaży nie będą systemowo identyfikowane jako zamówienia aplikacji Commerce. Ponadto te zamówienia wprowadzane przez tych użytkowników nie podlegają żadnym regułom przetwarzania finalizacji zamówień, logice ustalania cen ani innym weryfikacjom zamówień, które można definiować w konfiguracji kanału biura obsługi lub parametrach systemu biura obsługi.

Gdy skończysz konfigurować kanał biura obsługi i definiować użytkowników kanału, to w celu zagwarantowania pożądanego zachowania systemu upewnij się, że wszystkie wymagane parametry biura obsługi są zdefiniowane w oknie **Handel detaliczny i inny** \> **Ustawienia kanału** \> **Ustawienia biura obsługi** \> **Parametry biura obsługi**. Ponadto upewnij się, że są zdefiniowane powiązane numeracje.

> [!NOTE]
> Aby korzystać z funkcji biura obsługi, klucz konfiguracji dla opcji **Wielokrotna wysyłka** musi być włączony. Ten klucz konfiguracji można znaleźć w kluczach **konfiguracji handlu** w obszarze **Administracja systemem**\> **Instalator** \> **Konfiguracja licencji**. Jest to wymagane z powodu funkcji biura obsługi, która wykonuje różne operacje weryfikacji na podstawie adresu dostawy skonfigurowanego na poziomie wiersza zamówienia sprzedaży. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]