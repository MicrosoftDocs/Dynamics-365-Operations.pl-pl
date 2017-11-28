---
title: Ustawianie prognozowania popytu
description: "W tym temacie opisano ustawienia zadania, które należy wykonać, by przygotować się do prognozowania popytu."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 974edd06460df4afe594b0a033a042b8c2763f7f
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="demand-forecasting-setup"></a>Ustawianie prognozowania popytu

[!include[banner](../includes/banner.md)]


W tym temacie opisano ustawienia zadania, które należy wykonać, by przygotować się do prognozowania popytu.  

Zadania konfiguracji obejmują konfigurowanie następujących parametrów i danych.

## <a name="item-allocation-key"></a>Klucz alokacji produktów
Prognoza popytu jest obliczana dla towaru i jego wymiarów tylko wtedy, gdy towar jest częścią klucza alokacji towaru. Ta reguła zostaje wymuszona w celu pogrupowania dużej liczby towarów, tak aby można było szybciej utworzyć prognozy popytu. Procent klucza alokacji produktów jest ignorowany podczas generowania prognoz popytu. Prognozy są tworzone tylko na podstawie danych historycznych. 

Towar i jego wymiary muszą być częścią tylko jednego klucza alokacji produktów, o ile klucz jest używany podczas tworzenia prognozy. 

Aby dodać jednostkę magazynową do klucza alokacji produktów, przejdź do okna **Planowanie główne** &gt; **Ustawienia** &gt; **Prognozowania popytu** &gt; **Klucze alokacji produktu**. Na stronie **przypisywania towarów** przypisz produkty do klucza alokacji.

## <a name="intercompany-planning-groups"></a>Grupy planowania międzyfirmowego
Prognozowanie popytu generuje prognozy w obrębie firmy. W programie Microsoft Dynamics 365 for Finance and Operations, które są planowane razem, są grupowane w jednej grupie planowania międzyfirmowego. Aby określić dla każdej firmy, które klucze alokacji mają być brane pod uwagę przy prognozowaniu popytu, należy przypisać klucz alokacji produktów do członka grupy planowania międzyfirmowego, przechodząc do okna **Planowanie główne** &gt; **Ustawienia** &gt; **Grupy planowania międzyfirmowego**. 

Domyślnie, jeśli do członków grupy planowania firmowego nie są przypisane klucze alokacji produktów, prognoza popytu jest obliczana dla wszystkich pozycji przypisanych do wszystkich kluczy alokacji z wszystkich firm w programie Finance and Operations. Dodatkowe opcje filtrowania dla firm i klucze alokacji produktów są dostępne na stronie **generowania bazowej prognozy statystycznej**. 

Przejrzyj liczbę pozycji podlegających prognozie. Niepotrzebne pozycje mogą powodować zwiększenie kosztów, jeśli korzystasz z usługi uczenia maszynowego Microsoft Azure.

## <a name="demand-forecasting-parameters"></a>Parametry prognozowania popytu
Aby ustawić parametry prognozowania popytu, wybierz kolejno opcje **Planowanie główne** &gt; **Ustawienia** &gt; **Parametry prognozowania popytu**. Prognozowanie popytu jest uruchamiane w obrębie firmy, dlatego to ustawienie ma charakter globalny. Innymi słowy konfiguracja ma zastosowanie do wszystkich firm. 

Prognozowanie popytu generuje prognozy w ilościach. W związku z tym w polu **Jednostka prognozy popytu** należy określić jednostki miary, w których mają być wyrażone ilości. Jednostka miary musi być unikatowa w celu zagwarantowania, że agregacja i rozdział procentowy mają sens. Aby uzyskać więcej informacji o agregacji i rozdziale procentowym, zobacz [Ręczne korekty prognozy bazowej](manual-adjustments-baseline-forecast.md). Dla każdej jednostki miary używanej dla jednostek SKU zawartych w prognozie popytu należy sprawdzić, czy istnieje reguła konwersji dla jednostki miary i ogólna jednostka miary prognozowania. Po uruchomieniu prognozy rejestrowana jest lista towarów, które nie mają konwersji jednostki miary, ułatwiając wprowadzenie korekty w ustawieniach. 

Prognozowanie popytu może służyć do przewidywania zarówno zależnego, jak i niezależnego popytu. Jeśli na przykład zaznaczone jest tylko pole wyboru **Zamówienie sprzedaży** i jeśli wszystkie towary objęte prognozą są towarami, które są sprzedawane, system oblicza popyt niezależny. Można jednak dodawać składniki podrzędne o znaczeniu krytycznym do kluczy alokacji produktów i uwzględniać je w prognozie popytu. W takim przypadku jeśli zaznaczone jest pole wyboru **Wiersz produkcji**, obliczana jest prognoza zależna. 

Są dwie metody tworzenia prognozy bazowej w programie Finance and Operations. Modeli prognozowania można używać w oparciu o dane historyczne lub można te dane historyczne tylko skopiować do prognozy. Pole **Strategia generowania prognozy** pozwala wybrać między tymi dwoma metodami. Aby używać modeli prognozy, zaznacz opcję **Uczenie maszynowe Azure**. 

Klikając **Wymiary prognozy** w lewym okienku na stronie **Parametry prognozowania popytu**, możesz też wybrać zestaw wymiarów prognozy, które mają być używane przy generowaniu prognozy popytu. Wymiar prognozy wskazuje poziom szczegółów, które dla którego prognoza jest definiowana. Firma, oddział i klucz alokacji produktów są obowiązkowe w wymiarach prognozy, ale można również tworzyć prognozy na poziomie magazynu, stanu zapasów, grupy odbiorców, konta odbiorców, kraju/regionu, stanu i towaru oraz wymiaru wszystkich towarów. 

W dowolnym momencie można dodawać wymiary prognozy do listy wymiarów używanych do prognozowania popytu. Można też usunąć z listy wymiary prognozy. Ręczne korekty zostaną jednak utracone po dodaniu lub usunięciu wymiaru prognozy. 

Nie wszystkie towary zachowują się w taki sam sposób z perspektywy prognozowania popytu. Podobne towary mogą być pogrupowane w jeden klucz alokacji produktów i parametry, takie jak typy transakcji i ustawienia metod prognozy można ustawić według klucza alokacji produktów. Kliknij **Klucze alokacji produktów** w lewym okienku na stronie **Parametry prognozowania popytu**. 

Aby wygenerować prognozę, program Finance and Operations używa sieciowej usługi uczenia maszynowego. Aby połączyć się z usługą, trzeba wprowadzić do programu Finance and Operations następujące informacje podczas logowania do usługi Microsoft Azure Machine Learning Studio:

-   Klucz sieciowy API
-   Końcowy URL usługi sieciowej
-   Nazwa konta magazynu systemu Azure
-   Klucz konta magazynu systemu Azure

**Uwaga:** nazwa konta i klucz konta magazynu systemu są wymagane tylko w przypadku używania niestandardowego konta magazynu. Jeśli została wdrożona wersja lokalna programu, musisz mieć niestandardowe konto magazynu w systemie Azure, tak aby usługa uczenia maszynowego miała dostęp do danych historycznych. 

Aby utworzyć prognozy popytu, można wdrożyć własną usługę za pomocą platformy Machine Learning Studio lub eksperymentów prognozowania popytu dostępnych w programie Finance and Operations. Instrukcje wdrażania eksperymentów prognozowania popytu programu Finance and Operations jako usługi sieciowej są dostępne w programie Finance and Operations. Na stronie **Parametry prognozowania popytu** kliknij kartę **Uczenie maszynowe Azure**.

## <a name="settings-for-the-finance-and-operations-demand-forecasting-machine-learning-service"></a>Ustawienia usługi uczenia maszynowego prognozy popytu w programie Finance and Operations
Aby wyświetlić parametry, które można skonfigurować na potrzeby prognozowania usługi popytu w programie Finance and Operations, wybierz kolejno opcje **Planowanie główne** &gt; **Ustawienia** &gt; **Prognozowanie popytu** &gt; **Parametry algorytmu prognozowania**. Strona **Parametry algorytmu prognozowania** zawiera wartości domyślne parametrów. Można zastąpić te parametry na stronie **Parametry prognozowania popytu**. Na karcie **Ogólne** można zastąpi parametry globalnie lub użyć karty **Klucze alokacji produktów**, aby zastąpić te parametry według klucza alokacji produktów. Parametry, które są zastępowane dla klucza alokacji produktów mają wpływ tylko prognozę towarów, które są skojarzone z tym kluczem alokacji towaru.

<a name="see-also"></a>Informacje dodatkowe
--------

[Wprowadzenie do prognozowania popytu](introduction-demand-forecasting.md)

[Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md)

[Wprowadzanie ręcznych korekt prognozy bazowej](manual-adjustments-baseline-forecast.md)




