---
title: "Dodawanie formantu rekomendacji do strony transakcji na urządzeniu punktu sprzedaży"
description: "W tym temacie opisano sposób dodawania formantu rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w programie Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 47ad5dc8fd698f6f543c6a48e2c7eb01d4e148e6
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Dodawanie formantu rekomendacji do strony transakcji na urządzeniu punktu sprzedaży

[!include[banner](includes/banner.md)]


W tym temacie opisano sposób dodawania formantu rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w programie Microsoft Dynamics 365 for Retail.

Rekomendacje produktów mogą być wyświetlane na urządzeniu punktu sprzedaży podczas używania programu Microsoft Dynamics 365 for Retail. *Rekomendacje* to towary, którymi odbiorca może być zainteresowany w związku z wcześniej dokonywanymi zakupami, towary na liście życzeń odbiorcy oraz towary, które inni podobni odbiorcy kupowali w sklepach internetowych i tradycyjnych. Aby wyświetlać rekomendacje produktów, należy za pomocą projektanta układu ekranu dodać formant do ekranu transakcji.

## <a name="open-layout-designer"></a>Otwieranie projektanta układu
1.  Wybierz kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Punkt sprzedaży** &gt; **Układy ekranu**.
2.  Za pomocą szybkiego filtru znajdź ekran, do którego chcesz dodać formant. Na przykład wyfiltruj według pola **Identyfikator układu ekranu**, używając wartości „F2CP16:9M”.
3.  Na liście znajdź i zaznacz odpowiedni rekord. Na przykład zaznacz pozycję „Nazwa: F2CP16:9M Identyfikator układu ekranu: F2CP16:9M”.
4.  Kliknij opcję **Projektant układu**.
5.  Postępuj zgodnie z instrukcjami, aby uruchomić projektanta układu. Gdy zostanie wyświetlony monit o poświadczenia, wpisz te same poświadczenia, które były używane przy uruchamianiu konstruktora układu ze strony **Układy ekranu**.
6.  Po zalogowaniu się zobaczysz stronę podobną do przedstawionej poniżej. Układ może się różnić w zależności od dostosowań wprowadzonych dla sklepu.

[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Wybieranie opcji wyświetlania
-----------------------

Dostępne są dwie opcje konfiguracji. Wybierz opcję, która sprawdza się najlepiej dla Twojego sklepu, a następnie postępuj zgodnie z pozostałymi instrukcjami, aby dokończyć konfigurowanie formantu. Oto te opcje:
-   Rekomendacje są zawsze widoczne.
-   W siatce po prawej stronie ekranu jest wyświetlana karta **Zalecenia**.

#### <a name="to-make-recommendations-always-visible"></a>Aby rekomendacje były zawsze widoczne

1.  Zmniejsz wysokość obszaru szczegółów wierszy transakcji, tak aby była taka sama, jak wysokość panelu odbiorcy po lewej stronie.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)
2.  Z menu po lewej stronie przeciągnij formant rekomendacji i upuść go między obszar szczegółów wierszy transakcji a siatkę przycisków na środku w dolnej części ekranu transakcji. Zmień rozmiar formantu, tak aby mieścił się w tej przestrzeni.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)
3.  Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.
4.  W programie Dynamics 365 for Retail wybierz kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogramy dystrybucji**.
5.  Na liście zaznacz pozycję **1090 Kasy**.
6.  Kliknij przycisk **Uruchom teraz**.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Dodawanie karty Zalecenia do siatki przycisków po prawej stronie ekranu

1.  Kliknij prawym przyciskiem myszy puste miejsce pod ostatnią kartą w siatce przycisków umieszczoną z prawej strony ekranu.
2.  Kliknij przycisk **Dostosuj**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)
3.  Kliknij opcję **Nowa karta**.
4.  Znajdź nową kartę, który została właśnie dodana. Może być konieczne przewinięcie ekranu w dół.
5.  Na liście rozwijanej **Zawartość** wybierz opcję **Rekomendowane produkty**. [![pic-6](./media/pic-6.png)](./media/pic-6.png)
6.  W polu **Etykieta** wpisz nazwę karty rekomendacji. Na przykład wpisz „Zalecane produkty”.
7.  W polu **Obraz** zaznacz ilustrację, która ma być wyświetlana na karcie.
8.  Kliknij przycisk **OK** Nowa karta zostanie wyświetlone w siatce przycisków.
9.  Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.
10. W programie Dynamics 365 for Retail wybierz kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogramy dystrybucji**.
11. Na liście zaznacz pozycję **1090 Kasy**.
12. Kliknij przycisk **Uruchom teraz**.


<a name="see-also"></a>Informacje dodatkowe
--------

[Podstawowe informacje o spersonalizowanych rekomendacjach produktów](personalized-product-recommendations.md)




