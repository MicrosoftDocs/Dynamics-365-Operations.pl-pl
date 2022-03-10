---
title: Włącz spersonalizowane rekomendacje produktów
description: W tym temacie opisano sposób udostępniania spersonalizowanych rekomendacji dotyczących klientów w programie Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 74bf2c96d744b8101151be9288a956d46ce3b6885f0cb593dc1b78728b018fb4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770964"
---
# <a name="enable-personalized-recommendations"></a>Włączanie rekomendacji spersonalizowanych

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób udostępniania spersonalizowanych rekomendacji dotyczących klientów w programie Microsoft Dynamics 365 Commerce.

W systemie Dynamics 365 Commerce detaliści mogą udostępniać spersonalizowane rekomendacje dotyczące produktów (znane także jako Personalizacja). Dzięki temu spersonalizowane rekomendacje mogą być włączane do obsługi klienta w trybie online i w punkcie sprzedaży (POS). Gdy jest włączona funkcja personalizacji, system może skojarzyć informacje o zakupie i produkcie użytkownika w celu wygenerowania poszczególnych zaleceń dotyczących produktu.

## <a name="personalization-prerequisites"></a>Wymagania wstępne dotyczące personalizacji

Przed udostępnieniem klientom spersonalizowanych rekomendacji dotyczących produktów należy zauważyć, że zalecenia dotyczące produktów są obsługiwane tylko dla użytkowników systemu Commerce, którzy dokonali migracji swoich magazynów do usługi Azure Data Lake Store. Zanim klienci będą mogli uzyskać spersonalizowane zalecenia dotyczące produktów, muszą [włączyć rekomendacje produktów](enable-product-recommendations.md).

> [!NOTE]
> Włączając rekomendacje dotyczące produktów, Włącz również opcję Personalizacja. Jeśli jednak wyłączysz personalizację, nie wyłączasz innych typów rekomendacji dotyczących produktów.

Aby uzyskać więcej informacji na temat rekomendacji produktów, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).

## <a name="turn-on-personalization"></a>Włącz personalizację

Aby włączyć personalizację, należy wykonać następujące kroki.

1. W module Commerce Headquarters znajdź **Zarządzanie funkcjami**.
1. Opcja **Wszystkie** umożliwia wyświetlenie listy dostępnych funkcji. 
1. W polu wyszukiwania wprowadź **Rekomendacje**.
1. Wybierz funkcję **Spersonalizowane rekomendacje produktów**.
1. W okienku właściwości **Spersonalizowane rekomendacje produktów** wybierz opcję **Włącz teraz**.

![Włączanie personalizacji.](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> Po włączeniu personalizacji zostanie rozpoczęty proces generowania spersonalizowanych list rekomendacji produktów. Zanim te listy będą dostępne i widoczne w trybie online i w punkcie sprzedaży, może być wymagany maksymalnie jeden dzień.

## <a name="personalized-lists"></a>Spersonalizowane listy

Oprócz zezwalania na personalizację istniejących wygenerowanych przez komputer list, usługa rekomendacji umożliwia personalizację środowiska wykrywania produktów zarówno w trybie online, jak i w punkcie sprzedaży.

Po włączeniu personalizacji w terminalach punktu sprzedaży mogą być wyświetlane listy spersonalizowane „Wybrane dla Ciebie” lub „polecane klientom”. Ponadto Detaliści mogą zastosować personalizację do istniejących list rekomendacji produktów i dostarczać użytkownikom uwierzytelnionym użytkownikom ogólne rozporządzenie o ochronie danych (GDPR). Wyłączenie personalizacji powoduje również wyłączenie tych funkcji.

### <a name="online-picks-for-you-lists"></a>Listy „Wybrane dla Ciebie” w trybie online

Lista „Wybrane dla Ciebie” to sztuczna Lista materiałów do analizy (AI-ML), która pokazuje uwierzytelnionemu użytkownikowi spersonalizowaną listę sugerowanych produktów. Ta lista jest oparta na wielokanałowej historii zakupów użytkownika. Spersonalizowane rekomendacje są aktualizowane dynamicznie, gdy użytkownik dokonuje ponownych zakupów. Ten typ listy obsługuje również filtrowanie kategorii, dzięki czemu Detaliści mogą wyświetlać propozycje na podstawie hierarchii nawigacyjnych.

Zanim będzie można wyświetlić listę „Wybrane dla Ciebie” na stronie handlu elektronicznego, muszą zostać spełnione następujące wymagania użytkownika:

- Użytkownicy muszą być zalogowani. Użytkownicy anonimowi nie będą widzieli spersonalizowanych rekomendacji.
- Użytkownicy muszą mieć co najmniej jeden zakup na swoim koncie.
- Użytkownicy musieli wyrazić zgodę na otrzymywanie spersonalizowanych rekomendacji.

Na poniższej ilustracji przedstawiono przykład listy „Wybrane dla Ciebie” na stronie sklepu internetowego.

![Lista Wybrane dla Ciebie w trybie online.](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a>Listy „Wybrane dla Ciebie” w punkcie sprzedaży

Aby usprawnić usługi świadczone klientom, detaliści mogą personalizować istniejące strony szczegółów klientów, dodając listę kontekstową „Polecane klientom”.

Na poniższej ilustracji przedstawiono przykład listy „Polecane klientom” w terminalu punktu sprzedaży.

![Lista Wybrane dla Ciebie w punkcie sprzedaży.](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a>Zastosuj personalizację do istniejących list rekomendacji

Detaliści mogą zastosować personalizację do istniejących list rekomendacji, takich jak „nowe”, „popularne”, „Bestsellery”, „Klienci także lubią” i „Często kupowane razem”. Po zastosowaniu personalizacji do istniejących list z tych list są usuwane elementy, które zostały wcześniej zakupione przez zalogowanego użytkownika. Zarówno dla użytkowników anonimowych, jak i użytkowników, którzy zrezygnowali ze spersonalizowanych rekomendacji, zostaną wyświetlone domyślne wersje istniejących list. W związku z tym detaliści nie muszą ręcznie obsługiwać oddzielnych stron.

Na przykład użytkownik zalogowany już kupił czarny zegarem i brązowe buty robocze, które pojawią się na liście „popularne — domyślnie” na poniższej ilustracji. Dlatego użytkownik zobaczy nowe produkty zamiast tych produktów, tak jak to pokazano na liście „Popularne — spersonalizowane”.

![Trwa stosowanie personalizacji.](./media/applypersonalization.png)

Aby zastosować personalizację do istniejącej listy rekomendacji w module strony kreatora Commerce, wykonaj następujące kroki.

1. Otwórz istniejącą stronę konstruktora witryn zawierającą moduł zbierania produktów.
1. W okienku nawigacji po lewej stronie zaznacz moduł zbierania produktów.
1. W okienku nawigacji po prawej stronie, w obszarze **Produkty**, zaznacz listę.
1. W oknie dialogowym **Wybór konfiguracji listy produktów** w obszarze **typ** wybierz typ listy.
1. Zaznacz pole wyboru **Zastosuj personalizację**, a następnie kliknij przycisk **OK**.

    ![Stosowanie personalizacji do listy popularnych produktów.](./media/ApplyPersonalizationToTrending.PNG)

1. Zapisz stronę, zakończ jej edycję, a następnie ją opublikuj. Po opublikowaniu strony zalogowani użytkownicy będą widzieli spersonalizowane listy popularnych produktów.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie rekomendacji produktów](product-recommendations.md)

[Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce](enable-adls-environment.md)

[Włącz rekomendacje produktów](enable-product-recommendations.md)

[Włącz rekomendacje „Kup podobne”](shop-similar-looks.md)

[Rezygnowanie z rekomendacji spersonalizowanych](personalization-gdpr.md)

[Dodawanie rekomendacji produktu w punkcie sprzedaży](product.md)

[Dodawanie rekomendacji do ekranu transakcji](add-recommendations-control-pos-screen.md)

[Dostosowywanie wyników rekomendacji AI-ML](modify-product-recommendation-results.md)

[Ręczne tworzenie zaleceń pod opieką](create-editorial-recommendation-lists.md)

[Tworzenie rekomendacji z danymi demonstracyjnymi](product-recommendations-demo-data.md)

[Rekomendacje produktów — często zadawane pytania](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
