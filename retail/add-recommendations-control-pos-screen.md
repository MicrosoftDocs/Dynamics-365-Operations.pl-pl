---
title: "Dodawanie formantu zalecenia ze stroną transakcji na urządzeniu POS"
description: "W tym temacie opisano sposób dodawania formantu zalecenia do ekranu transakcji w punkcie sprzedaży (POS) urządzenia przy użyciu Projektant układu ekranu w systemie Microsoft Dynamics 365 dla operacji."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2377b1639a3c95fe6bba4754c4069cc12043e3d3
ms.lasthandoff: 03/31/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Dodawanie formantu zalecenia ze stroną transakcji na urządzeniu POS

W tym temacie opisano sposób dodawania formantu zalecenia do ekranu transakcji w punkcie sprzedaży (POS) urządzenia przy użyciu Projektant układu ekranu w systemie Microsoft Dynamics 365 dla operacji.

Rekomendacje produktów można wyświetlić na urządzeniu punktu sprzedaży przy użyciu usługi Microsoft Dynamics 365 dla operacji. *Zalecenia* są elementy, które klient może być zainteresowany opartych na ich historii zakupów, elementy w ich życzeń i elementy innych klientów kupić w trybie online i w sklepach z cegły i zaprawy. Aby wyświetlić rekomendacje produktów, należy dodać formant na ekranie transakcji za pomocą Projektant układu ekranu.

## <a name="open-layout-designer"></a>Otwórz projektanta układu
1.  Przejdź do **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**POS**&gt;**ekranu układy**.
2.  Umożliwia znajdowanie ekranu, który chcesz dodać formant do szybkiego filtrowania. Na przykład, filtrować według **identyfikator układu ekranu** pola, używając wartości 'F2CP16:9M'.
3.  Na liście znajdź i zaznacz odpowiedni rekord. Na przykład, zaznacz ' Nazwa: Identyfikator układu ekranu F2CP16:9M: F2CP16:9M ".
4.  Kliknij **Konstruktor układu**.
5.  Postępuj zgodnie z instrukcjami, aby uruchomić konstruktora układu. Gdy zostanie wyświetlony monit o poświadczenia, wpisz te same poświadczenia, które były używane po uruchomieniu konstruktora układu z **ekranu układy** strony.
6.  Po zalogowaniu, zostanie wyświetlona strona podobny do przedstawionego poniżej. Układ może się różnić w zależności od dostosowań, które zostały wprowadzone dla Twojego Sklepu.

[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) wybierz opcję wyświetlania
-----------------------

Możliwe są dwie opcje konfiguracji. Wybierz opcję, która najlepiej swojego Sklepu, a następnie postępuj zgodnie z wyświetlanymi instrukcjami, aby zakończyć konfigurowanie formantu. Dostępne są następujące dwie opcje:
-   Zalecenia są zawsze widoczne.
-   A **zalecenia** tab zostanie wyświetlone w siatce po prawej stronie ekranu.

#### <a name="to-make-recommendations-always-visible"></a>Wydaje zalecenia zawsze widoczne

1.  Zmniejsz wysokość obszaru szczegółów wierszy transakcji, tak, że jest tej samej wysokości co panel klienta po lewej stronie. [](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)
2.  Z menu po lewej stronie przeciągnij i upuść formant zalecenia pomiędzy obszarem szczegóły wiersza transakcji i siatki przycisków na środku dolnej części ekranu transakcji. Zmień rozmiar formantu, tak aby pasował w tym pomieszczeniu. [](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)
3.  Kliknij **X** Aby zapisać i zamknąć konstruktora układu.
4.  W usłudze Dynamics 365 dla operacji, przejdź do **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramy dystrybucji**.
5.  Z listy wybierz **rejestruje 1090**.
6.  Kliknij **Uruchom teraz**.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Aby dodać kartę zalecenia do siatki przycisków po prawej stronie ekranu

1.  Kliknij prawym przyciskiem myszy puste miejsce pod ostatnią kartę na siatkę przycisków znajdujących się po prawej stronie strony.
2.  Kliknij **dostosować**. [![pic-5](./media/pic-5.png)](./media/pic-5.png)
3.  Kliknij **Nowa karta**.
4.  Znajdź nową kartę, który został właśnie dodany. Może być konieczne przewinięcie w dół.
5.  W **treści** listę rozwijaną, wybierz opcję **zalecane produkty**. [![PIC-6](./media/pic-6.png)](./media/pic-6.png)
6.  W **etykiety** wpisz nazwę zalecenia kartę. Na przykład wpisz "Produkty zalecane".
7.  W **obrazu** pól, należy zaznaczyć obraz pojawi się na karcie.
8.  Click **OK**. Nowa karta zostanie wyświetlone w siatce przycisku.
9.  Kliknij **X** Aby zapisać i zamknąć konstruktora układu.
10. W usłudze Dynamics 365 dla operacji, przejdź do **sieci sprzedaży i handlu**&gt;**Retail IT**&gt;**harmonogramy dystrybucji**.
11. Z listy wybierz **rejestruje 1090**.
12. Kliknij **Uruchom teraz**.


<a name="see-also"></a>Informacje dodatkowe
--------

[Przegląd zaleceń spersonalizowanych produktów](personalized-product-recommendations.md)


