---
title: Dodawanie rekomendacji do ekranu transakcji
description: W tym temacie opisano sposób dodawania kontrolki rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: af2450b27106325a86f6db68f9791637694cda63
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665087"
---
# <a name="add-recommendations-to-the-transaction-screen"></a>Dodawanie rekomendacji do ekranu transakcji

[!include [banner](includes/banner.md)]


W tym temacie opisano sposób dodawania kontrolki rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w Microsoft Dynamics 365 Commerce. Aby uzyskać więcej informacji na temat zaleceń dotyczących produktów, zapoznaj się z [zaleceniami dotyczącymi produktów w dokumentacji punktu sprzedaży](product.md).


Rekomendacje produktów mogą być wyświetlane na urządzeniu punktu sprzedaży podczas używania Commerce. Aby wyświetlać rekomendacje produktów, należy za pomocą projektanta układu ekranu dodać formant do ekranu transakcji. 

## <a name="open-layout-designer"></a>Otwieranie projektanta układu

1. Wybierz kolejno opcje **Retail i Commerce** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Punkt sprzedaży** &gt; **Układy ekranu**.
2. Za pomocą szybkiego filtru znajdź ekran, do którego chcesz dodać formant. Na przykład wyfiltruj według pola **Identyfikator układu ekranu**, używając wartości **F2CP16:9M**.
3. Na liście znajdź i zaznacz odpowiedni rekord. Na przykład zaznacz pozycję **Nazwa: F2CP16:9M Identyfikator układu ekranu: F2CP16:9M**.
4. Kliknij opcję **Projektant układu**.
5. Postępuj zgodnie z instrukcjami, aby uruchomić projektanta układu. Gdy zostanie wyświetlony monit o poświadczeniach, wpisz te same poświadczenia, które były używane przy uruchamianiu projektanta układu ze strony **Układy ekranu**.
6. Po zalogowaniu się zobaczysz stronę podobną do przedstawionej poniżej. Układ może się różnić w zależności od dostosowań wprowadzonych dla sklepu.


    [![Projektant układu](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Wybierz opcję wyświetlaną

Dostępne są dwie opcje konfiguracji. Wybierz opcję, która sprawdza się najlepiej dla Twojego sklepu, a następnie postępuj zgodnie z pozostałymi instrukcjami, aby dokończyć konfigurowanie formantu. Oto te opcje:

- Rekomendacje są zawsze widoczne.
- W siatce po prawej stronie ekranu jest wyświetlana karta **Zalecenia**.

### <a name="make-recommendations-always-visible"></a>Rekomendacje zawsze widoczne


1. Zmniejsz wysokość obszaru szczegółów wierszy transakcji, tak aby była taka sama, jak wysokość panelu odbiorcy po lewej stronie.


    [![Zmniejszona wysokość obszaru szczegółów wierszy transakcji](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. Z menu po lewej stronie przeciągnij formant rekomendacji i upuść go między obszar szczegółów wierszy transakcji a siatkę przycisków na środku w dolnej części ekranu transakcji. Zmień rozmiar formantu, tak aby mieścił się w tej przestrzeni.

    [![Formant rekomendacji dodany do układu](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)


3. Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.
4. W Commerce wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Dane IT sprzedaży** &gt; **Harmonogramy dystrybucji**.
5. Na liście zaznacz pozycję **1090 Kasy**.
6. Kliknij przycisk **Uruchom teraz**.


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Dodawanie karty Zalecenia do siatki przycisków po prawej stronie ekranu

1. Kliknij prawym przyciskiem myszy puste miejsce pod ostatnią kartą w siatce przycisków umieszczoną z prawej strony ekranu.

2. Kliknij **Dostosuj**.

    [![Dostosowywanie — okno dialogowe Formant karty](./media/pic-5.png)](./media/pic-5.png)

3. Kliknij opcję **Nowa karta**.
4. Znajdź nową kartę, który została właśnie dodana. Może być konieczne przewinięcie w dół.
5. Na liście rozwijanej **Zawartość** wybierz opcję **Rekomendowane produkty**.

    [![Wybieranie Rekomendowanych produktów w polu Zawartość](./media/pic-6.png)](./media/pic-6.png)

6. W polu **Etykieta** wpisz nazwę karty rekomendacji. Na przykład wpisz „Zalecane produkty”.
7. W polu **Obraz** zaznacz ilustrację, która ma być wyświetlana na karcie.
8. Kliknij przycisk **OK**. Nowa karta zostanie wyświetlone w siatce przycisków.
9. Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.
10. W Commerce wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Dane IT sprzedaży** &gt; **Harmonogramy dystrybucji**.
11. Na liście zaznacz pozycję **1090 Kasy**.
12. Kliknij przycisk **Uruchom teraz**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Włącz rekomendacje „Kup podobne”](shop-similar-looks.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)
