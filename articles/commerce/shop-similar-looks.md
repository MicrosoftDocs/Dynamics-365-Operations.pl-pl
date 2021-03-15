---
title: Włącz rekomendacje „Kup podobne”
description: W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 95e4246d6c5f9ac5bc86b626be0d971f756c5130
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985618"
---
# <a name="enable-shop-similar-looks-recommendations"></a>Włącz rekomendacje „Kup podobne”

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób włączenia zaleceń dotyczących produktu „kup podobne” w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Funkcja rekomendacji „kup podobne” w Dynamics 365 Commerce wykorzystuje moc sztucznej inteligencji i uczenia maszynowego (AI-ML) do dostarczania klientom rekomendacji dotyczących wizualnie podobnych produktów. Udostępniając rekomendacje „kupuj podobne” dla wszystkich kanałów sprzedaży detalicznej w usłudze Commerce, sprzedawcy mogą zwiększyć satysfakcję klientów, pomagając klientom łatwo znaleźć to, czego szukają.

Funkcja rekomendacji „kup podobne” wykorzystuje zdjęcia produktów wariantów produktów nasiennych, aby znaleźć i polecić wizualnie podobne produkty w katalogu produktów sprzedawcy. 

Rekomendacje „Kup podobne” są dostępne zarówno w punktach sprzedaży (POS), jak i w rozwiązań handlu elektronicznego.

### <a name="example-scenarios"></a>Przykładowe scenariusze

- Klient ogląda czarny sweter w paski i otrzymuje rekomendację dotyczącą podobnego swetra w kolorze czerwonym. Klient wybiera rekomendowany produkt zamiast pierwotnie oglądanego produktu, a następnie otrzymuje rekomendacje podobnych produktów w kolorze czerwonym. 
- Klient korzysta z zaleceń „Kup podobne”, aby odkryć kolczyki pasujące do pierścionka, którymi jest zainteresowany kupujący.

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a>Włącz rekomendacje „Kup podobne” w Commerce headquarters

Zalecenia dotyczące produktów są obsługiwane tylko dla użytkowników Commerce, którzy przeprowadzili migrację magazynu do Azure Data Lake Gen2.

### <a name="prerequisites"></a>Wymagania wstępne

Zanim sprzedawcy zaczną wyświetlać klientom rekomendacje „kupuj podobny wygląd”, musisz wykonać dwa wstępne kroki:

- [Włącz rekomendacje produktów](enable-product-recommendations.md) w Commerce Headquarter.
- Upewnij się, że serwer multimediów obsługuje połączenia HTTPS.

Aby aparat zaleceń mógł uzyskać dostęp do obrazów produktu, detaliści muszą wygenerować adresy URL produktów. Aby wygenerować adresy URL produktów w centrali Commerce headquarters, wykonaj następujące kroki.

1. Przejdź do **Obrazy produktu**.
1. W okienku akcji wybierz opcję **Definiuj szablon multimediów**.
1. W okienku właściowości **Definiuj szablon multimediów** w obszarze **Adresy URL multimediów** wybierz opcję **Generuj adresy URL**.

> [!NOTE]
> Po włączeniu funkcji rekomendacji „kup podobne” rozpoczyna się proces generowania list rekomendacji produktów. Może minąć nawet jeden dzień, zanim listy te będą dostępne i widoczne w Internecie i na terminalach POS.

Aby włączyć funkcję rekomendacji „Kup podobne” w centrali Commerce, wykonaj następujące kroki.

1. Przejdź do obszaru **Zarządzanie funkcjami**.
1. Na liście dostępnych funkcji wyszukaj i wybierz pozycję **Kup podobne**.
1. W prawym okienku wybierz opcję **Włącz**, aby włączyć usługę.

Na poniższej ilustracji przedstawiono funkcję **Kup podobne** na stronie **Zarządzanie funkcjami** w module Commerce Headquarter.

![Funkcja Sklep podobny wygląda na stronie zarządzania funkcjami w siedzibie Commerce](./media/enableshopsimilarlooks.png)

Po zakończeniu powyższych zadań terminale POS są automatycznie rozszerzane za pomocą panelu **Kup podobne produkty**. Po wybraniu opcji **Zobacz więcej**, użytkownicy terminalu w punkcie sprzedaży mogą zostać uwzględnieni w dedykowanej stronie „kup podobne”, którą można później przefiltrować.

> [!NOTE]
> Jeśli wyłączysz funkcję rekomendacji „Kup podobne”, nie ma to wpływu na inne typy rekomendacji produktów. Aby uzyskać więcej informacji na temat rekomendacji produktów, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a>Dodaj przycisk „Kup podobne” do stron szczegółów produktu za pomocą narzędzia do tworzenia witryn Commerce

Po włączeniu funkcji rekomendacji „kup podobny wygląd” w centrali Commerce, opcja w narzędziu do tworzenia witryn Commerce umożliwia sprzedawcom detalicznym dodanie przycisku **Kup podobne** do pola zakupu na dowolnej stronie szczegółów produktu (PDP). Klient, który wybierze ten przycisk, zostaje przeniesiony na specjalną stronę „Kup podobne produkty”, która zwraca wizualnie podobne produkty. W tym celu odbiorca może wykorzystać selektory do dalszego filtrowania produktów.

Aby dodać przycisk **Kup podobne** do stron PDP za pomocą narzędzia do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Otwórz istniejącą stronę konstruktora witryn zawierającą moduł pola zakupu.
1. W okienku nawigacji po lewej stronie zaznacz moduł pola zakupu.
1. W prawym okienku nawigacji zaznacz pole wyboru **Włącz łącze zakup podobne**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować. Po opublikowaniu strony PDP będzie zawierała przycisk **Kup podobne**.

Na poniższej ilustracji przedstawiono pole wyboru **Włącz łącze zakup podobne** i **Kup podobne** na przykładowej PDP w konstruktorze witryn.

![Włącz pole wyboru Kupuj podobne i przycisk Kupuj podobne na PDP w narzędziu do tworzenia witryn](./media/SSLecomtooling.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]