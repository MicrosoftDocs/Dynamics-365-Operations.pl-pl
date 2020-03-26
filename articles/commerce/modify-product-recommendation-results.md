---
title: Dostosowanie wyników rekomendacji produktów na podstawie plików AI-ML
description: W tym temacie wyjaśniono sposób dostosowywania wyników propozycji produktów na podstawie sztucznej inteligencji dotyczącej wywiadu (AI-ML) w firmie.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4631ef03e1d73b70d80e774d1efa4909e619bbc0
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127935"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a>Dostosowanie wyników rekomendacji produktów na podstawie plików AI-ML


[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono sposób dostosowywania wyników propozycji produktów na podstawie sztucznej inteligencji dotyczącej wywiadu (AI-ML) w firmie. 

Po włączeniu zaleceń dotyczących produktu ustawienia domyślne zaczną obowiązywać; te parametry mogą działać dla wielu potrzeb. Najlepiej zaplanować poświęcenie pewnego czasu oceny, czy wyniki są zgodne ze sprzedażą produktów. Sugerujemy ocenę wyników przez kilka dni przed zmianą parametrów w razie potrzeby przed ponownym rozpoczęciem testowania. 

## <a name="understanding-recommendation-list-parameters"></a>Zrozumienie parametrów listy rekomendacji

Przed zmianą parametrów Dowiedz się, jak będą one wpływać na wyniki poniżej.

### <a name="trending-product-list"></a>Lista „popularnych” produktów

Lista „popularnych” produktów zawiera dwa parametry, który można zmienić:

![Przykładowy domyślny parametr listy „popularnych” produktów](./media/exampletrendingparameters.png)

1. **Uwzględnij nowe produkty z ostatnich X dni** — produkty dodane w ciągu określonej liczby dni przed bieżącą datą można użyć do wybrania kandydatów produktów. Wartość domyślna na obrazie sugeruje, że produkty starsze niż 180 dni mogą być używane na liście produktów trendu.
1. **Obejmuje sprzedaż z ostatnich X dni** - Transakcje sprzedaży, które miały miejsce w ciągu określonej liczby dni przed bieżącą datą, można wykorzystać do zamówienia produktów. Wartość domyślna powyżej sugeruje, że wszystkie zakupy produktu w ciągu ostatnich 30 dni zostałyby użyte w celu ustalenia położenia produktu na liście produktów trendu. 

### <a name="best-selling-product-list"></a>Lista „bestsellerów”

W zależności od prowadzonej działalności „bestsellery” mogą mieć różne wyniki niż trendy, nawet jeśli używają one danych transakcji do zamawiania produktów. Ponieważ lista bestsellerów nie ma odcięcia na podstawie daty asortymentu, bestsellery nadal mogą być wyróżnione jako bardzo popularne, starsze produkty, które mogły zostać usunięte z listy trendów. 

Lista „bestsellery” zawiera jeden parametr, który można zmienić:

![Przykładowy domyślny parametr listy bestsellerów](./media/examplebestsellingparameters.PNG)

1. **Obejmuje sprzedaż z ostatnich X dni** - Transakcje sprzedaży, które miały miejsce w ciągu określonej liczby dni przed bieżącą datą, można wykorzystać do zamówienia produktów. Wartość domyślna powyżej sugeruje, że wszystkie zakupy produktu w ciągu ostatnich 30 dni zostałyby użyte w celu ustalenia położenia produktu na liście produktów bestsellerów. 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a>Ręczne dodawanie lub usuwanie produktów z list rekomendacji

### <a name="for-new-trending-or-best-selling-lists"></a>W przypadku list „nowości”, „trendów” lub „bestsellerów”

1.  Przejdź do **Handel detaliczny i komercyjny** > **Rekomendacje produktów** > **Właściwości rekomendacji**.
1.  Na liście udostępnionych parametrów sieci sprzedaży wybierz **listy rekomendacji**.
1.  Wybierz listę dodaj lub usuń produkty.
1.  Aby dodać produkty do tabeli, wybierz **Dodaj wiersz**. 
1.  W kolumnie produkt Wyszukaj produkt według jego **nazwy** lub **numeru produktu**.

    ![Przykład wyszukiwania produktu na liście nowych produktów](./media/examplenewlistconfiguration1.png)

1.  W kolumnie Typ wiersza wybierz jedną z dwóch opcji:
    -   **Uwzględnij** — wymusza wymuszenie produktu z przodu listy
    -   **Wyklucz** — usuwa produkt z listy
    
    ![Przykład uwzględniania lub wykluczania produktu z listy nowych produktów](./media/examplenewlistconfiguration2.png)

1.  Zmiana **kolejności wyświetlania** zmieni kolejność, gdy produkty oznaczone jako **uwzględnione** zostaną wyświetlone na liście.
    - Jeśli dwa produkty mają taką samą wartość **kolejności wyświetlania**, ostateczna kolejność tych dwóch wyników może się różnić od biura zaplecza.
1.  Aby usunąć produkty z tabeli: zaznacz wiersz do usunięcia i wybierz opcję **Usuń**.


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a>Dla list „Inni często lubią” lub „często kupowane razem”

W kontekście list „Często kupowane razem” lub „Klientom podoba się również”, uczenie maszynowe służy do analizy wzorców zakupów konsumenckich w celu rekomendowania powiązanych produktów, które są wspólnie kupowane dla unikalnego produktu początkowego. 
 
*Produkt początkowy* to produkt, dla którego mają być generowane wyniki. W kontekście ręcznego dostosowywania list rekomendacji są dodawane lub usuwane wyniki dla tego produktu. 

Aby ręcznie dodać lub usunąć wyniki dla produktu początkowego, należy wykonać następujące czynności:
1.  Wybierz **Produkt początkowy**. 
1.  W kolumnie **produkt** wyszukaj produkt według jego **nazwy** lub **numeru produktu.**
![Przykład wyszukiwania produktu na nowej liście produktów najczęściej kupowanych razem](./media/exampleFBTlistconfiguration1.png)
1. W kolumnie **Typ wiersza** wybierz jedną z dwóch opcji:
    - **Uwzględnij** — wymusza wymuszenie produktu z przodu listy
    - **Wyklucz** — usuwa produkt z listy     
![Przykład uwzględniania lub wyłączania produktu na liście produktów najczęściej kupowanych razem](./media/exampleFBTlistconfiguration2.png)
1.  Aby usunąć produkty z tabeli: zaznacz wiersz do usunięcia i wybierz opcję Usuń.


## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie ADLS w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Dodawanie list rekomendacji produktów do witryny handlu elektronicznego](add-reco-list-to-page.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)
