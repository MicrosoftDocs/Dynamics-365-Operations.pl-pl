---
title: Ustawianie prognozowania popytu
description: W tym temacie opisano ustawienia zadania, które należy wykonać, by przygotować się do prognozowania popytu.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 623e9efc1c8fc1001b9aedc42c563eaa25afb3ba
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207070"
---
# <a name="demand-forecasting-setup"></a>Ustawianie prognozowania popytu

[!include [banner](../includes/banner.md)]

W tym temacie opisano ustawienia zadania, które należy wykonać, by przygotować się do prognozowania popytu.  

Zadania konfiguracji obejmują konfigurowanie następujących parametrów i danych.

## <a name="item-allocation-key"></a>Klucz alokacji produktów
Prognoza popytu jest obliczana dla towaru i jego wymiarów tylko wtedy, gdy towar jest częścią klucza alokacji towaru. Ta reguła zostaje wymuszona w celu pogrupowania dużej liczby towarów, tak aby można było szybciej utworzyć prognozy popytu. Procent klucza alokacji produktów jest ignorowany podczas generowania prognoz popytu. Prognozy są tworzone tylko na podstawie danych historycznych. 

Towar i jego wymiary muszą być częścią tylko jednego klucza alokacji produktów, o ile klucz jest używany podczas tworzenia prognozy. 

Aby dodać jednostkę magazynową do klucza alokacji produktów, przejdź do okna **Planowanie główne** &gt; **Ustawienia** &gt; **Prognozowania popytu** &gt; **Klucze alokacji produktu**. Na stronie **przypisywania towarów** przypisz produkty do klucza alokacji.

## <a name="intercompany-planning-groups"></a>Grupy planowania międzyfirmowego
Prognozowanie popytu generuje prognozy w obrębie firmy. W Dynamics 365 Supply Chain Management firmy, które są planowane razem są grupowane w jednej grupie planowania międzyfirmowego. Aby określić dla każdej firmy, które klucze alokacji mają być brane pod uwagę przy prognozowaniu popytu, należy przypisać klucz alokacji produktów do członka grupy planowania międzyfirmowego, przechodząc do okna **Planowanie główne** &gt; **Ustawienia** &gt; **Grupy planowania międzyfirmowego**. 

Domyślnie, jeśli do członków grupy planowania firmowego nie są przypisane klucze alokacji produktów, prognoza popytu jest obliczana dla wszystkich pozycji przypisanych do wszystkich kluczy alokacji z wszystkich firm. Dodatkowe opcje filtrowania dla firm i klucze alokacji produktów są dostępne na stronie **generowania bazowej prognozy statystycznej**. 

Przejrzyj liczbę pozycji podlegających prognozie. Niepotrzebne pozycje mogą powodować zwiększenie kosztów, jeśli korzystasz z usługi uczenia maszynowego Microsoft Azure.

## <a name="demand-forecasting-parameters"></a>Parametry prognozowania popytu
Aby ustawić parametry prognozowania popytu, wybierz kolejno opcje **Planowanie główne** &gt; **Ustawienia** &gt; **Parametry prognozowania popytu**. Prognozowanie popytu jest uruchamiane w obrębie firmy, dlatego to ustawienie ma charakter globalny. Innymi słowy konfiguracja ma zastosowanie do wszystkich firm. 

Prognozowanie popytu generuje prognozy w ilościach. W związku z tym w polu **Jednostka prognozy popytu** należy określić jednostki miary, w których mają być wyrażone ilości. Jednostka miary musi być unikatowa w celu zagwarantowania, że agregacja i rozdział procentowy mają sens. Aby uzyskać więcej informacji o agregacji i rozdziale procentowym, zobacz [Ręczne korekty prognozy bazowej](manual-adjustments-baseline-forecast.md). Dla każdej jednostki miary używanej dla jednostek SKU zawartych w prognozie popytu należy sprawdzić, czy istnieje reguła konwersji dla jednostki miary i ogólna jednostka miary prognozowania. Po uruchomieniu prognozy rejestrowana jest lista towarów, które nie mają konwersji jednostki miary, ułatwiając wprowadzenie korekty w ustawieniach. 

Prognozowanie popytu może służyć do przewidywania zarówno zależnego, jak i niezależnego popytu. Jeśli na przykład zaznaczone jest tylko pole wyboru **Zamówienie sprzedaży** i jeśli wszystkie towary objęte prognozą są towarami, które są sprzedawane, system oblicza popyt niezależny. Można jednak dodawać składniki podrzędne o znaczeniu krytycznym do kluczy alokacji produktów i uwzględniać je w prognozie popytu. W takim przypadku jeśli zaznaczone jest pole wyboru **Wiersz produkcji**, obliczana jest prognoza zależna. 

Są dwie metody tworzenia prognozy bazowej. Modeli prognozowania można używać w oparciu o dane historyczne lub można te dane historyczne tylko skopiować do prognozy. Pole **Strategia generowania prognozy** pozwala wybrać między tymi dwoma metodami. Aby używać modeli prognozy, zaznacz opcję **Uczenie maszynowe Azure**. 

Klikając **Wymiary prognozy** w lewym okienku na stronie **Parametry prognozowania popytu**, możesz też wybrać zestaw wymiarów prognozy, które mają być używane przy generowaniu prognozy popytu. Wymiar prognozy wskazuje poziom szczegółów, które dla którego prognoza jest definiowana. Firma, oddział i klucz alokacji produktów są obowiązkowe w wymiarach prognozy, ale można również tworzyć prognozy na poziomie magazynu, stanu zapasów, grupy odbiorców, konta odbiorców, kraju/regionu, stanu i towaru oraz wymiaru wszystkich towarów. 

W dowolnym momencie można dodawać wymiary prognozy do listy wymiarów używanych do prognozowania popytu. Można też usunąć z listy wymiary prognozy. Ręczne korekty zostaną jednak utracone po dodaniu lub usunięciu wymiaru prognozy. 

Nie wszystkie towary zachowują się w taki sam sposób z perspektywy prognozowania popytu. Podobne towary mogą być pogrupowane w jeden klucz alokacji produktów i parametry, takie jak typy transakcji i ustawienia metod prognozy można ustawić według klucza alokacji produktów. Kliknij **Klucze alokacji produktów** w lewym okienku na stronie **Parametry prognozowania popytu**. 

Aby wygenerować prognozę, Supply Chain Management używa sieciowej usługi uczenia maszynowego. Aby połączyć się z usługą, trzeba wprowadzić następujące informacje podczas logowania do usługi Microsoft Azure Machine Learning Studio (wersja klasyczna):

-   Klucz sieciowy API
-   Końcowy URL usługi sieciowej
-   Nazwa konta magazynu systemu Azure
-   Klucz konta magazynu systemu Azure

> [!NOTE]
> Nazwa konta i klucz konta magazynu Azure systemu są wymagane tylko w przypadku używania niestandardowego konta magazynu. Jeśli została wdrożona wersja lokalna programu, musisz mieć niestandardowe konto magazynu na platformie Azure, tak aby usługa Machine Learning miała dostęp do danych historycznych. 

Aby utworzyć prognozy popytu, można wdrożyć własną usługę za pomocą platformy Machine Learning Studio lub eksperymentów prognozowania popytu dostępnych Supply Chain Management. Instrukcje wdrażania eksperymentów prognozowania popytu jako usługi sieciowe są dostępne w programie Supply Chain Management. Na stronie **Parametry prognozowania popytu** kliknij kartę **Uczenie maszynowe Azure**.

## <a name="settings-for-the-demand-forecasting-machine-learning-service"></a>Ustawienia usługi uczenia maszynowego prognozy popytu.
Aby wyświetlić parametry, które można skonfigurować na potrzeby usługi prognozowania popytu, wybierz kolejno opcje **Planowanie główne** &gt; **Ustawienia** &gt; **Prognozowanie popytu** &gt; **Parametry algorytmu prognozowania**. Strona **Parametry algorytmu prognozowania** zawiera wartości domyślne parametrów. Można zastąpić te parametry na stronie **Parametry prognozowania popytu**. Na karcie **Ogólne** można zastąpi parametry globalnie lub użyć karty **Klucze alokacji produktów**, aby zastąpić te parametry według klucza alokacji produktów. Parametry, które są zastępowane dla klucza alokacji produktów mają wpływ tylko prognozę towarów, które są skojarzone z tym kluczem alokacji towaru.

### <a name="forecast-algorithm-parameters"></a>Parametry algorytmu prognozy

Na karcie **Klucze alokacji** można określić **Parametry algorytmu prognozy** prognozy dla każdego klucza alokacji produktów. Dostępne są następujące opcje.
- **Wartość procentowa poziomu ufności**: Przedział wiarygodności zawiera zakres wartości będących dobrymi danymi szacunkowymi dla prognozy popytu. Wiarygodność na poziomie 95% oznacza, że występuje 5-procentowe ryzyko, że w przyszłości popyt wykroczy poza zakres wiarygodności.
- **Wymuszaj sezonowość**: Określa, czy w modelu ma być używany określony typ sezonowości. Dotyczy to tylko ARIMA i ETS only. Opcje: AUTOMATYCZNE (domyślne), BRAK, DADATKOWE, ZWIELOKROTNIONE.
- **Model prognozowania**: Opcje: ARIMA, ETS, STL, ETS + ARIMA, ETS + STL, ALL. Aby wybrać model najlepszego dopasowania, należy skorzystaćz opcji **WSZYSTKIE**.
- **Maksymalna wartość prognozy**: Określa maksymalną wartość, która ma być użyta dla prognoz. Format: + 1E[n] lub stała numeryczna.
- **Minimalna wartość prognozy**: Określa minimalną wartość, która ma być użyta dla prognoz. Format: - 1E[n] lub stała numeryczna.
- **Brak podstawiania wartości**: Określa sposób wypełniania przerw w danych historycznych. Opcje: wartość liczbowa, ŚREDNIA, POPRZEDNIA, INTERPOLACJA LINIOWA, INTERPOLACJA WIELOMIANOWA.
- **Brak zakresu podstawiania wartości**: Określa, czy podstawianie wartości ma zastosowanie tylko do zakresu danych każdego z poszczególnych atrybutów stopnia szczegółowości, czy do całego zestawu danych. Opcje: GRANULARITY_ATTRIBUTE (domyślny), GLOBALNY.
- **Wskazówka sezonowości**: W przypadku danych sezonowych należy wprowadzić wskazówkę do modelu prognozowania w celu zwiększenia dokładności prognozy. Format: liczba całkowita, reprezentująca liczbę przedziałów powtórzeń wzoru popytu. Na przykład wprowadź wartość „6” dla danych, które powtarzają się co 6 miesięcy.
- **Procent rozmiaru zestawu testowego**: Procent danych historycznych przeznaczonych do użycia jako zestaw testowy w obliczeniach dokładności prognozy. 

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie prognozowania popytu](introduction-demand-forecasting.md)

[Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md)

[Wprowadzanie ręcznych korekt prognozy bazowej](manual-adjustments-baseline-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]