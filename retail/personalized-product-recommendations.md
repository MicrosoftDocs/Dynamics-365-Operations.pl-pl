---
title: "Przegląd zaleceń spersonalizowanych produktów"
description: "W usłudze Dynamics 365 dla operacji zalecenia produktów mogą być wyświetlane jest punkt sprzedaży (POS) urządzenia. Zalecenia są elementy, które klient może być zainteresowany opartych na ich historii zakupów, elementy w ich życzeń i elementy innych klientów kupić w trybie online i w sklepach z cegły i zaprawy. Dla sprzedawców o dużych katalogów zalecenia pomocy klientom z odnajdywaniem produktu. Publikując produkty ukierunkowane na klienta interesy i nawyki kupujących, zalecenia produktu może pomóc sprzedawców w sprzedaży i cross selling i może zwiększyć zatrzymania odbiorcy. W usłudze Dynamics 365 dla operacji zalecenia produktu są zasilane przez usługi poznawcze i uczenie maszynowe Microsoft Azure."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: af1f4ba1ed5efe0e35d08d37d09e7ada4a4c1b7a
ms.lasthandoff: 03/31/2017


---

# <a name="personalized-product-recommendations-overview"></a>Przegląd zaleceń spersonalizowanych produktów

W usłudze Dynamics 365 dla operacji zalecenia produktów mogą być wyświetlane jest punkt sprzedaży (POS) urządzenia. Zalecenia są elementy, które klient może być zainteresowany opartych na ich historii zakupów, elementy w ich życzeń i elementy innych klientów kupić w trybie online i w sklepach z cegły i zaprawy. Dla sprzedawców o dużych katalogów zalecenia pomocy klientom z odnajdywaniem produktu. Publikując produkty ukierunkowane na klienta interesy i nawyki kupujących, zalecenia produktu może pomóc sprzedawców w sprzedaży i cross selling i może zwiększyć zatrzymania odbiorcy. W usłudze Dynamics 365 dla operacji zalecenia produktu są zasilane przez usługi poznawcze i uczenie maszynowe Microsoft Azure.

<a name="scenarios"></a>Scenariusze
---------

Rekomendacje produktów są włączone w następujących scenariuszach POS. Są one dostępne w chmurze POS lub nowoczesnych POS (MPOS).

1.  Na **szczegóły produktu** stronę:

-   Jeśli Magazyn skojarzyć wizyty **szczegóły produktu** stronę przy spojrzenie na wcześniejsze transakcje różnych kanałów, aparat zalecenie proponuje dodatkowe elementy, które są mogą być zakupiona razem.
-   Jeśli pracownik sklepu doda odbiorcy do transakcji i następnie wizyty **szczegóły produktu** strona, zalecenie silnik zawiera spersonalizowane rekomendacje przy użyciu historii transakcji odbiorcy.

[![proddetails](./media/proddetails.png)](./media/proddetails.png)

1.  Na **transakcji** stronę:

-   Aparat zalecenie proponuje elementów opartych na całą listę towarów w koszyku.
-   Jeśli pracownik sklepu doda odbiorcy do transakcji, aparat zalecenie zapewnia spersonalizowane rekomendacje przy użyciu historii transakcji odbiorcy i na liście elementów w koszyku.

**Uwaga** do wyświetlania zalecenia na **transakcji** strony, sprzedawca detaliczny musi zaktualizować układ ekranu w usłudze Dynamics 365 dla operacji. **Zalecenia** kontroli musi być odrzucone, do **transakcji** strony. [![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

1.  Na **szczegóły klienta** stronę:
    -   Aparat zalecenie proponuje elementów na podstawie Identyfikatora użytkownika i elementy listy życzeń klienta.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Konfigurowanie 365 Dynamics dla włączania zalecenia POS
Aby skonfigurować zalecenia produktu, należy wykonać następujące czynności.

1.  Upewnij się, że wybrano poprawne **firmy**.
2.  Przejdź do **magazynu jednostki**, wybierz opcję **sprzedaż detaliczna**, a następnie kliknij przycisk **Odśwież**. ** ** to użycia danych demonstracyjnych (lub danych) z bazy danych operacyjnych i przenieść go do magazynu jednostki.
3.  Opcjonalnie: Aby wyświetlić zalecenia na ekranie transakcji, przejdź do ** układ ekranu, **wybierz układ ekranu, uruchamianie **Projektant układu ekranu**,** **, a następnie upuść ** kontroli zalecenia ** w razie potrzeby.
4.  Przejdź do **handlu detalicznego parametry**, wybierz opcję **uczenie maszynowe**, wybierz opcję ** tak ** pod **zalecenia POS po**.
5.  Aby wyświetlić zalecenia w punkcie sprzedaży, należy uruchomić zadanie konfiguracji globalnej **1110**. Aby odzwierciedlić zmiany wprowadzone w POS Projektant układu ekranu, należy uruchomić zadanie konfiguracji kanału **1070**.

## <a name="how-does-it-work"></a>[]()Jak to działa?
Gdy odświeżasz **magazyn jednostki** encji, zostaną wykonane następujące czynności.

-   Dane w formacie wymagane przez służby poznawcze ekstrahuje się z 365 Dynamics dla operacji operacyjnej bazy danych i wysyłane do sklepu encji.
-   Dane jest używany przez fabryki danych Azure (ADF) do czyszczenia danych przy użyciu skryptów gałąź w ramach działalności automatycznego podajnika dokumentów. Oczyszczoną dane są przechowywane w magazynie obiektów blob.
-   Dane z magazynu obiektów blob jest używany przez interfejs API usług poznawcze szkolić modelu zalecenia.

Po włączeniu **włączyć zalecenia** i uruchamiać zadania konfiguracji, zostaną wykonane następujące czynności.

-   Wzór poświadczenia i identyfikator są zabierani z interfejsu API i przechowywane w usłudze Dynamics 365 dla operacji operacyjnej bazy danych, w pliku web.config dla serwera AOS, a także w tym serwerze.
-   Wzór poświadczenia i identyfikator są udostępnione CRT tak, że wzywa do zaleceń produktu z chmury POS i MPOS w trybie online może być przestrzegana.


<a name="see-also"></a>Informacje dodatkowe
--------

[Dodawanie formantu zalecenia ze stroną transakcji na urządzeniu POS](add-recommendations-control-pos-screen.md)


