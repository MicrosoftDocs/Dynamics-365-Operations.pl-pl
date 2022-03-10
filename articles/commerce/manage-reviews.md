---
title: Zarządzanie ocenami i recenzjami
description: W tym temacie wyjaśniono, jak zarządzać klasyfikacjami recenzjami konstruktorze witryn Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1aefa6eb93ef251778a48ba972d87e0cd5930bf0
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968234"
---
# <a name="manage-ratings-and-reviews"></a>Zarządzanie ocenami i recenzjami

[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono, jak zarządzać klasyfikacjami recenzjami konstruktorze witryn Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce uzywa Microsoft Azure Cognitive Service do automatyczniej moderacji tekstu recenzji, redagując wulgaryzmy Ponadto za pomocą konstruktora witryn Dynamics 365 Commerce moderatorzy mogą wykonywać następujące zadania ręczne:

- Moderowanie recenzji, odpowiadając na nie lub usuwaniu.
- Usuwanie opini klienta na jego życzenie.
- Masowe Importowanie danych ocen i recenzji dotyczących wszystkich produktów w szablonie rozwiązania Microsoft Power BI, dzięki czemu można analizować trendy dotyczące ocen i recenzji.

## <a name="read-a-review"></a>Przeczytaj recenzję 

Aby przeczytać recenzję w konstruktorze witryn w usłudze Commerce, wykonaj następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Moderacja**
1. Pole wyszukiwania w prawym górnym rogu strony umożliwia filtrowanie recenzji wyświetlanych według identyfikatora produktu, nazwy produktu lub tekstu recenzji.

Dodatkowe filtry umożliwiają ograniczenie recenzji według okresu, oceny, kanału lub oddziału (odrzucenia, odpowiedzi lub zgłoszenia).

![Strona główna moderacji.](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a>Odpowiedz na recenzję 

Czasami Klienci, którzy zakupili produkt, wyrażają zadowolenie lub niedozadowolenie, lub nie wiedzą, jak skorzystać z produktu. Jako moderatora możesz zaksięgować odpowiedź na recenzję. Ta odpowiedź jest wyświetlana razem z recenzją w witrynie. 

Aby odpowiedzieć na recenzję w konstruktorze witryn w usłudze Commerce, wykonaj następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Moderacja**
1. Znajdź i wybierz recenzję, która wymaga odpowiedzi.
1. W panelu właściwości po prawej wybierz **Dodaj odpowiedź**.
1. Wprowadź tekst odpowiedzi i nazwę, która powinna być wyświetlana dla obiektu odpowiadającego. Domyślną nazwą obiektu odpowiadającego jest **moderator**.
1. Po zakończeniu wybierz przycisk **Prześlij odpowiedź**.

![Odpowiedź na recenzję.](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a>Zapoznaj się z recenzją 

Niekiedy w firmie istnieje uzasadnienie biznesowe w celu usunięcia recenzji klientów. 

Aby usunąć recenzję w konstruktorze witryn w usłudze Commerce, wykonaj następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Moderacja**
1. Znajdź i zaznacz recenzję, która ma zostać przewidziana.
1. W okienku właściwości po prawej stronie wybierz przyczynę usunięcia w obszarze **Usuń recenzję**, a następnie wybierz opcję **Usuń**.
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a>Usuwanie opini klienta na jego życzenie 

Czasami klienci chcą trwale usunąć swoje oceny i dane z witryny internetowej e-Commerce. Moderator otrzymujący żądanie usunięcia od odbiorcy może usunąć dane odbiorcy, korzystając z funkcji usuwania recenzji. Aby znaleźć i usunąć dane odbiorcy, moderator wymaga adresu e-mail używanego przez klienta do zalogowania się i dostarczenia recenzji. 

Aby znaleźć i usunąć dane klienta w konstruktorze witryn w module Commerce, należy wykonać następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Usuń**
1. W polu **Wyszukaj użytkowników według adresu e-mail** wprowadź adres e-mail odbiorcy, a następnie wybierz opcję **Szukaj**.
1. Jeśli odbiorca ma jakiekolwiek czynności recenzowania (na przykład: wysłane recenzje, głosy na temat użyteczności recenzji innych odbiorców lub komentarze dotyczące recenzji innego odbiorcy), zostaną wyświetlone wyniki. Dla każdego towaru jest dostępny przycisk **Usuń**.
1. Dla każdego towaru, który musi zostać usunięty, wybierz opcję **Usuń**. Po wyświetleniu monitu o potwierdzenie wybierz opcję **tak**. 
    
![Usuwanie danych klienta.](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - W celu całkowitego usunięcia danych z systemu może upłynąć nawet do siedmiu dni. Moderatorzy powinni powiadamiać odbiorców o tym opóźnieniu.
> - Jeśli odbiorcy zmienili swoje nazwisko w ustawieniach konta, w wynikach wyszukiwania może pojawić się wiele elementów. W takim przypadku, aby całkowicie usunąć dane odbiorcy, moderator musi wybrać opcję **Usuń** dla każdego towaru. 

## <a name="download-ratings-and-reviews-data"></a>Pobieranie danych ocen i recenzji

Konstruktor witryn w module Commerce pozwala moderatorom na masowe importowanie ocen i recenzji, dzięki czemu mogą analizować trendy. Dostępny jest szablon Power BI zawierający podstawowe miary. Moderatorzy mogą używać tego szablonu do łączenia danych importowanych zbiorczo i przeglądania pulpitu nawigacyjnego. Nie muszą oni tworzyć niestandardowych pulpitów nawigacyjnych. Moderatorzy mogą również dostosować szablon Power BI w celu spełnienia określonych wymagań. 

Aby pobrać dane ocen i recenzji w konstruktorze witryn w module Commerce, należy wykonać następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Raportowanie**
1. Wybierz opcję **Pobierz dane recenzji**, aby pobrać oceny i recenzje danych luzem w formacie CSV (wartości rozdzielane przecinkami).

## <a name="view-ratings-and-reviews-trends"></a>zobacz trendy ocen i recenzji

Moderatorzy mogą pobrać szablon Power BI, aby umożliwić wyświetlanie trendów na pulpicie nawigacyjnym.

Aby wyświetlić trendy ocen i recenzji w konstruktorze witryn w module Commerce, należy wykonać następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Raportowanie**
1. Wybierz opcję **Szablon usługi PowerBI**, aby pobrać szablon.

    ![Pobieranie szablonu Power BI.](media/rnr-moderation-reports.png) 

1. Otwórz pobrany szablon za pomocą aplikacji Power BI. Zamknij okno dialogowe **Dostęp do zawartości sieci Web**, które zostanie wyświetlone, a następnie zamknij wyświetlony komunikat o błędzie „Odśwież”.
1. Przejdź do **strony głównej**, wybierz opcję **Edytuj kwerendy**, a następnie wybierz **Ustawienia źródła danych**.
1. W oknie dialogowym **ustawienia źródła danych** wybierz opcję **Zmień źródło**.
1. W polu **adres URL** wprowadź ścieżkę danych recenzji, które zostały pobrane w poprzedniej procedurze (na przykład **c:\\reviews\\ReviewsData.csv**).

    ![Pole adresu URL w oknie dialogowym wartości rozdzielane przecinkami.](media/rnr-powerbi-datasource-settings.png) 

1. Wybierz  **OK** i kliknij przycisk **Zastosuj zmiany**. Zastosowanie zmian w źródle danych będzie trwać jedną do dwóch minut.
1. Wybierz opcję **Arkusz trendów**, aby wyświetlić trendy dotyczące ocen i recenzji.

    ![Trendy ocen i recenzji.](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](ratings-reviews-overview.md)

[Zgoda na korzystanie z ocen i recenzji](opt-in-ratings-reviews.md)

[Konfigurowanie ocen i recenzji](configure-ratings-reviews.md)

[Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail](sync-product-ratings.md)

[Włączanie ręcznego publikowania ocen i recenzji przez moderatora](manual-publish-rating-reviews.md)

[Importowanie i eksportowanie klasyfikacji oraz przeglądów](import-export-reviews.md)

[Konfigurowanie uwierzytelniania usługa-usługa](service-to-service-auth.md)

[Oceny i recenzje — często zadawane pytania](ratings-reviews-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
