---
title: Ocenianie modelu początkowych prognoz płatności odbiorcy (wersja zapoznawcza)
description: W tym temacie opisano kroki, które można wykonać w celu zrozumienia zasad działania modelu przewidywania płatności od odbiorców i oceny jego skuteczności.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: ef0daec6153405fc064b1185ba7067796ff5bb45
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995122"
---
# <a name="evaluate-the-initial-customer-payment-prediction-model-preview"></a>Ocenianie modelu początkowych prognoz płatności odbiorcy (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak oceniać model przewidywania po włączeniu modułu Finance Insights, a następnie wygenerowaniu i wytrenowaniu pierwszego modelu. Ten temat dotyczy modeli służących do przewidywania płatności od odbiorców. Opisano w nim kroki, które można wykonać w celu zrozumienia zasad działania modelu przewidywania płatności od odbiorców i oceny jego skuteczności.

## <a name="getting-details-about-the-model"></a>Uzyskiwanie szczegółowych informacji o modelu

W systemie Microsoft Dynamics 365 Finance na stronie **Parametry Finance Insights** obok wyniku dokładności jest wyświetlane łącze **Zwiększ dokładność modelu**.

[![Łącze Zwiększ dokładność modelu](./media/prediction-model.png)](./media/prediction-model.png)

To łącze prowadzi do aplikacji AI Builder, gdzie można uzyskać więcej informacji na temat bieżącego modelu, a także podejmować kroki w celu jego ulepszenia. Poniższa ilustracja przedstawia stronę, która zostanie otwarta.

[![AI Builder](./media/what-to-predict.png)](./media/what-to-predict.png)

Na stronie, która zostanie otwarta, znajdują się następujące informacje:

- W sekcji **Wydajność** ocena punktowa wydajności modelu daje perspektywę jakość modelu. Aby uzyskać więcej informacji o tej ocenie punktowej, zapoznaj się z tematem [Wydajność modelu przewidywania](https://docs.microsoft.com/ai-builder/prediction-performance) w dokumentacji aplikacji AI Builder.
- Sekcja **Dane o największym wpływie** pokazuje, jak ważne są różne typy danych wejściowych dla modelu. Można ocenić zawartość tej listy i towarzyszące wartości procentowe w celu określenia, czy informacje są zgodne z Twoją wiedzą o firmie o rynku.

    [![Sekcje Wydajność i Dane o największym wpływie w modelu przewidywania](./media/models.png)](./media/models.png)

- W sekcji **Wydajność** wybierz opcję **Zobacz szczegóły**, aby dowiedzieć się więcej o ocenie punktowej i innych zagadnieniach. Na poniższej ilustracji szczegóły pokazują, że model używa mniej informacji, niż jest to zalecane. W związku z tym system wygenerował komunikat ostrzegawczy.

    [![Ostrzeżenia dotyczące wydajności modelu](./media/details.png)](./media/details.png)

## <a name="digging-deeper"></a>Zagłębianie się

Chociaż dokładność jest dobrym punktem wyjściowym w ocenie modelu, a ocena punktowa wydajności daje perspektywę, aplikacja AI Builder dostarcza bardziej szczegółowe wskaźniki, które będzie można wykorzystać podczas oceny. Aby pobrać szczegóły, w sekcji **Wydajność** kliknij przycisk wielokropka (**...**) widoczny obok przycisku **Użyj modelu**, a następnie wybierz opcję **Pobierz szczegółowe metryki**.

[![Polecenie Pobierz szczegółowe metryki](./media/performance.png)](./media/performance.png)

Na poniższej ilustracji przedstawiono format, w którym można pobrać dane.

[![Format pobieranych danych](./media/data-format.png)](./media/data-format.png)

Aby dokonać głębszej analizy wyników, dobrym punktem wyjściowym jest zapoznanie się z metryką „Matryca pomyłek”. Na przykład oto dane wyświetlane dla tej metryki na poprzedniej ilustracji.

`{"name": "Confusion Matrix", "value": {"schema_type": "confusion_matrix", "schema_version": "1.0.0", "data": {"class_labels": ["0", "1", "2"], "matrix": [[71, 9, 21], [5, 0, 27], [2, 0, 45]]}}, "type": "dictionaryNumericalList", "isGlobalScore": false}`

Te dane można rozwinąć w następujący sposób:

|                          | Przewidywane na czas | Przewidywane opóźnienie | Przewidywane duże opóźnienie |
|--------------------------|-------------------|----------------|---------------------|
| Faktyczna płatność na czas   | **71**            | 0              | 21                  |
| Faktyczna opóźniona płatność      | 5                 | **0**          | 27                  |
| Faktyczna bardzo opóźniona płatność | 2                 | 0              | **45**              |

W matrycy pomyłek są wyświetlane wyniki losowo wybranego zestawu danych testowych z procesu trenowania. Ponieważ te zamknięte faktury nie zostały użyte do trenowania modelu, są dobrymi przypadkami testowymi dla modelu. Ponadto, ponieważ znany jest rzeczywisty stan faktury, widać także wydajność modelu.

Pierwszą rzeczą, na którą należy zwrócić uwagę, jest najczęściej występująca wartość rzeczywista. Chociaż ta wartość może nie reprezentować idealnie całego zestawu danych, jest dobrym przybliżeniem. W tym przypadku **Faktyczna płatność na czas** występuje w 92 na 171 faktur ogółem, dlatego jest najczęściej występującą wartością rzeczywistą. Dlatego jest dobrym punktem odniesienia dla modelu. Jeśli wcześniej zakładano, że wszystkie faktury zostaną zapłacone na czas, to przewidywanie sprawdziłoby się w 92 na 171 przypadków (czyli w 54%).

Ważne jest, aby znać zbilansowanie zawartości zestawu danych. W tym przypadku spośród 171 faktur 92 zapłacono na czas, 32 z opóźnieniem, a 47 z dużym opóźnieniem. Te wartości wskazują na dobre zbilansowanie zestawu danych, ponieważ w każdej klasyfikacji nie ma nieistotnej zawartości. Sytuacja, w której jeden z tych stanów zawierałby bardzo mało wyników, stanowiłaby duże wyzwanie dla modelu uczenia maszynowego.

Dokładność modelu wskazuje liczbę prawidłowych przewidywań dla zestawu danych testowych. Te poprawne przewidywania to wartości, które są wyświetlane pogrubioną czcionką w poprzednim przykładzie. W tym przypadku wartości dają obliczoną dokładność 67,8 procent (= \[71 + 0 + 45\] ÷ 171). Ta wartość oznacza poprawę o 14 procent względem bazowego przypuszczenia wynoszącego 54 procent i jest jednym ze wskaźników jakości modelu.

Jeśli przyjrzysz się bliżej matrycy pomyłek, zauważysz, że model radzi sobie dobrze z przewidywaniem płatności na czas i bardzo opóźnionych. Jednak pomylił się dla wszystkich 32 faktur zapłaconych z opóźnieniem (ale nie bardzo dużym opóźnieniem). Ten wynik sugeruje, że jest wymagana dodatkowa eksploracja i udoskonalenie modelu.

Liczbą reprezentującą wydajność modelu lepiej niż dokładność jest wynik Makro F1. Ten wynik punktowy uwzględnia wyniki każdego stanu klasyfikacji (na czas, opóźnione i bardzo opóźnione). Na przykład oto dane wyświetlane dla metryki „Makro F1” na poprzedniej ilustracji.

`{"name": "F1 Macro", "value": 0.4927170868347339, "type": "percentage", "isGlobalScore": false}`

W tym przypadku wynik punktowy metryki Makro F1 wynoszący około 49,3 procent wskazuje, że model nie zapewnia skutecznego prognozowania dla każdego stanu, pomimo ogólnego wyniku dokładności wyglądającego na wysoki.

## <a name="improving-the-model"></a>Ulepszanie modelu

Po dokładniejszym zrozumieniu wyników uzyskiwanych przez pierwszy model można spróbować go ulepszać, dodając lub usuwając kolumny cech albo odfiltrowując części zestawu danych, które nie przyczyniają się do dokładności prognoz. Zamknij aplikację AI Builder, a następnie w systemie Dynamics 365 Finance użyj łącza **Ulepsz model**, aby od nowa rozpocząć proces w aplikacji AI Builder. Możesz eksperymentować z różnymi cechami bez wpływania na opublikowany model. Opublikowany model zmieni się dopiero po wybraniu opcji **Publikuj**. Pamiętaj, że w wystąpieniu usługi Dynamics 365 Finance jest używany tylko jeden model. Dlatego przed opublikowaniem jakiegokolwiek nowego modelu należy go uważnie sprawdzić.

## <a name="for-more-information"></a>Więcej informacji

Aby uzyskać więcej informacji na temat sposobu oceny modeli przewidywania, zobacz [Wyniki modeli uczenia maszynowego](/confusion-matrix.md).

#### <a name="privacy-notice"></a>Klauzula prywatności
Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.
