---
title: Omówienie rekomendacji produktów
description: Ten temat zawiera ogólne informacje o rekomendacjach produktu. Rekomendacje produktów umożliwiają łatwe i szybkie znajdowanie produktów, które są potrzebne, a nawet produktów, których klient nie zamierzał pierwotnie kupić.
author: Moonma
ms.date: 05/26/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7824de50a65370ef4f2f23b9c8e926f9bec2fcc3
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982126"
---
# <a name="product-recommendations-overview"></a>Omówienie rekomendacji produktów

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce może posłużyć do pokazywania zaleceń dotyczących produktów w witrynie e-Commerce i urządzeniach punktu sprzedaży (POS). Rekomendacje produktów to przedmioty, które mogą być interesujące dla odbiorcy. Rekomendacje są oparte na trendach zakupu innych odbiorców w sklepach internetowych oraz w sklepach tradycyjnych.

Zalecenia dotyczące produktów pozwalają klientom łatwo i szybko znaleźć produkty, których chcą, mając doświadczenie, które im dobrze służy. Można nawet użyć sprzedaży powiązanej i oferowanie droższego produktu, aby pomóc klientom znalezienie dodatkowych produktów niż pierwotnie zamierzone. Kiedy rekomendacje są pomocne w odkrywaniu produktów, mogą stworzyć więcej możliwości konwersji, pomóc zwiększyć przychody ze sprzedaży, a nawet pomóc zwiększyć satysfakcję i utrzymanie klientów.

W handlu elektronicznym rekomendacje produktów są oparte na technologiach uczenia maszynowego rekomendacji Microsoft na dużą skalę.

Ta usługa jest dodatkiem do Dynamics 365 Commerce. Aby uzyskać więcej informacji, pobierz najnowszy [Podręcznik licencjonowania rozwiązania Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).


## <a name="recommendation-service"></a>Usługa rekomendacji

Usługa rekomendacji produktów korzysta z sztucznych technologii wywiadu i nauki maszyn (AI) w następujący sposób:

- Dane w formacie wymaganym przez usługę rekomendacji są pobierane z operacyjnej bazy danych Commerce i wysyłane do Azure Data Lake Storage lub magazynu jednostek.
- Usługa rekomendacji korzysta z przechowywanych danych w celu wytrenowania modeli rekomendacji dla list **Klientom podoba się również**, **Często kupowane razem**, **Nowości**, **Bestsellery** i **Trendy**.

## <a name="scenarios"></a>Scenariusze

Rekomendacje produktów są dostępne w opisanych niżej scenariuszach:

- **Na dowolnej stronie sklepu lub stronie magazynowej w e-Commerce:** Jeśli klient lub sprzedawca odwiedza stronę sklepu, aparat rekomendacji może sugerować produkty na listach **Nowości**, **Bestsellery** i **Trendy**.
- **Na stronie Szczegóły produktu:** Jeśli klienci lub sprzedawcy odwiedzają stronę **Szczegóły produktu**, aparat rekomendacji sugeruje dodatkowe towary, które również prawdopodobnie zostaną nabyte. Pozycje te pojawiają się również na liście osoby **Klientom podoba się również**.
- **Na stronie transakcja lub stronie realizacja transakcji:** aparat rekomendacji sugeruje pozycje na podstawie całej listy towarów w koszyku. Te pozycje są wyświetlane na liście **Często kupowane razem**.
- **Spersonalizowane rekomendacje:** Sprzedawcy mogą dostarczać zalogowanym odbiorcom listę **Wybrane dla Ciebie** w dodatku do nowych funkcji, które pozwalają na spersonalizowanie istniejących scenariuszy list na podstawie tego odbiorcy. Aby dowiedzieć się więcej, patrz [Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md).

### <a name="types-of-product-recommendations"></a>Typy rekomendacji produktów

W poniższej tabeli opisano różne typy automatycznych rekomendacji dotyczących produktów dostępnych dla detalistów, które można zaimplementować w rozwiązaniu Dynamics 365 Commerce za pośrednictwem [modułu zbierania produktów](product-collection-module-overview.md). Detaliści mogą także wyświetlać spersonalizowane wyniki dla zalogowanego użytkownika, jeśli autor witryny wybierze tę opcję.

| Moduł kolekcji produktów  | Typ | opis |
|----------------------------|------|-------------|
| Nowy element                        | Algorytmy | Ten moduł pokazuje listę najnowszych produktów w najnowszych asortymentach do kanałów i katalogów. |
| Bestsellery               | Algorytmy | Ten moduł pokazuje listę produktów sklasyfikowanych według najwyższej liczby sprzedaży. |
| Popularne                   | Algorytmy | Ten moduł listę produktów najwyższej wydajności w danym okresie, sklasyfikowanych według najwyższej liczby sprzedaży.  |
| Często kupowane razem | AI-ML | W tym module zaleca listę produktów, które są często kupowane razem z zawartością bieżącego koszyka konsumentów. |
| Klienci także lubią           | AI-ML | Ten moduł zaleca produkty dla danego inicjatora na podstawie wzorców zakupów odbiorców. |
| Wybrane dla Ciebie              | AI-ML | Ten moduł zaleca spersonalizowaną listę produktów na podstawie wzorców zakupów zalogowanego użytkownika. W przypadku użytkownika gościa ta lista zostanie zwinięta. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Włączanie rekomendacji spersonalizowanych](personalized-recommendations.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Włącz rekomendacje „Kup podobne”](shop-similar-looks.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
