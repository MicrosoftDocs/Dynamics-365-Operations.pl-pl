---
title: Wprowadzanie ręcznych korekt prognozy bazowej
description: W tym temacie wyjaśniono, jak wprowadzać ręczne korekty prognozy bazowej i jak wyświetlać szczegóły prognozy.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9dc5d1812fa926216a75b6fc4e3cf820ccc3ef6d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435461"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>Wprowadzanie ręcznych korekt prognozy bazowej

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak wprowadzać ręczne korekty prognozy bazowej i jak wyświetlać szczegóły prognozy. 

Przed dokonaniem ręcznych korekt bardzo ważne jest, aby zapoznać się z kilkoma koncepcjami na różnych stronach.

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>Siatka na stronie Skorygowana prognoza popytu
Strona **Skorygowana prognoza popytu** zawiera siatkę, która oferuje następującą strukturę:

-   Pierwsza kolumna pokazuje towary, klucze alokacji produktów, firmy itd., dla których wygenerowano prognozę. Podtytuł strony zawiera opis bieżących wymiarów prognozy, które są widoczne na siatce. Jeśli na przykład strona ma podtytuł **Firma / Oddział / Klucz alokacji produktów**, a jeden z nagłówków wierszy w siatce to **USMF / 1 / D\_Alloc**, ten wiersz pokazuje prognozę dla oddziału 1 firmy USMF i klucza alokacji produktów **D\_Alloc**.
-   Kolejne kolumny zawierają przedziały prognozy, dla których prognoza została wygenerowana. Każdy nagłówek kolumny jest pierwszą datą przedziału prognozy, jaka jest widoczna w kolumnie.
-   Wartości w komórkach pokazują prognozę dla jednego towaru, klucza alokacji produktów itd, dla określonego przedziału prognozy.

## <a name="forecast-aggregation-and-de-aggregation"></a>Agregacja i deagregacja prognozy
Podtytuł strony pokazuje poziom agregacji prognozy. 

Na przykład, jeśli strona ma podtytuł **Firma / Oddział / Klucza alokacji / Kod towaru / Kolor / Rozmiar / Konfiguracja / Style**, nie ma żadnej agregacji prognozy i prognoza jest wyświetlana na poziomie towaru i jego wymiarów. Aby zmienić agregację, użyj strony **Zmień wymiary prognozy**, który można otworzyć z menu aplikacji. 

Aby zmodyfikować prognozę, kliknij dowolną z dostępnych komórek i wpisz skorygowaną wartość prognozy. Zmieniona komórka natychmiast staje się pogrubiona, wskazując, że widoczna w niej prognoza nie została utworzona przez usługę prognozowania popytu, ale została ręcznie skorygowana. 

Jeśli zmienisz agregację w celu zwiększenia ilości danych wyświetlanych na stronie, możesz użyć strony **Wiersze prognozy popytu**, aby wyświetlić poszczególne wiersze prognozy tworzące sumaryczną prognozę. 

Na przykład została wygenerowana prognoza na poziomie towaru, ale wiadomo, że popyt na ten towar wzrośnie we wszystkich oddziałach ze względu na promocję lub innego rodzaju podobne zdarzenie. W takim przypadku można ustawić agregację na **Firma / Klucz alokacji produktów / Towar** na stronie **Zmień wymiary prognozy**. Globalne skorygować globalną prognozę dla towaru we wszystkich oddziałach na siatce **Skorygowana prognoza popytu**. Aby zobaczyć efekt zmian we wszystkich oddziałach, otwórz stronę **Wiersze prognozy popytu**. Na tej stronie będzie widoczny jeden wiersz dla towaru w każdym oddziale, skorygowaną prognozowaną ilość i pierwotną prognozowaną ilość. 

Po skorygowaniu prognozowanej ilości na poziomie sumarycznym system używa alokacji ważonej do dystrybucji zmiany w wierszach tworzących agregację. 

Można też wprowadzać ręczne korekty na stronie **Wiersze prognozy popytu**, zmieniając wartość **Ilość całkowita** lub komórki **Ilość** na siatce deagregacji.

## <a name="viewing-details-of-the-forecast"></a>Wyświetlanie szczegółów prognozy
Można otworzyć stronę **Szczegóły prognozy popytu**, aby wyświetlić więcej informacji na temat prognozy. 

Strona **Szczegóły prognozy popytu** pokazuje następujące informacje na grafice i w tabeli:

-   Popyt historyczny, na którym opierają się przewidywania prognozy.
-   Bieżąca prognoza używana przez Planowanie główne.
-   Nowe wartości prognozy popytu i kwoty, o które zostały one ręcznie skorygowane.
-   Przedział wiarygodności dla prognozowanych wartości.
-   Model prognozy używany do generowania prognozy. Przy przeglądaniu danych sumarycznych pojawi się lista wszystkich metod używanych dla wszystkich serii czasu łącznego.
-   Wewnętrzny model dokładności (MAPE). Aby uzyskać więcej informacji o dokładności prognozy, zobacz [Monitorowanie dokładności prognozy](monitor-forecast-accuracy.md).

**Uwagi:**

-   Jeśli zostanie włączone **wybieranie modelu prognozy dla szczegółów prognozy popytu** w obszarze zarządzania funkcjami, będzie można wybrać modele prognozy do uwzględnienia dla prognozy historycznej, na stronie **Szczegóły prognozy popytu**.
-   Przedział wiarygodności widoczny w sekcji **Prognoza** na stronie przedstawia różnicę między górnym i dolnym limitem przedziału wiarygodności. Aby wyświetlić wartości limitów górnych i dolnych, umieść wskaźnik myszy na wykresie w sekcji **Graficzna prezentacja popytu historycznego i prognozy**.
-   W przypadku korzystania z usługi Microsoft Azure Machine Learning dla prognozowania popytu można określić wymagany procent poziomu zaufania dla generowanej prognozy. Przedział wiarygodności zawiera zakres wartości będących dobrymi danymi szacunkowymi dla prognozy popytu. Wiarygodność na poziomie 95% oznacza, że występuje 5-procentowe ryzyko, że prognoza popytu wykroczy poza zakres wiarygodności.

Istnieje również możliwość ręcznego korygowania prognozy na stronie **Szczegóły prognozy popytu** poprzez modyfikację wartości w wierszu **Prognoza** w sekcji **Prognoza**.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Monitorowanie dokładności prognozy](monitor-forecast-accuracy.md)

[Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md)



