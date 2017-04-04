---
title: Ustawianie prognozowania popytu
description: "W tym temacie opisano ustawienia zadania, które należy wykonać, by przygotować się do prognozowania popytu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f629329f4f50bd7c8edcfd70641bace01a1c53aa
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-setup"></a>Ustawianie prognozowania popytu

W tym temacie opisano ustawienia zadania, które należy wykonać, by przygotować się do prognozowania popytu.  

Zadania konfiguracji obejmują konfigurowanie następujących parametrów i danych.

## <a name="item-allocation-key"></a>Klucz alokacji produktów
Prognoza popytu jest obliczana dla towaru i jego wymiarów tylko wtedy, gdy towar jest częścią klucza alokacji towaru. Ta reguła jest wymuszane do grupy dużej liczby elementów, tak, że można szybciej utworzyć prognoz popytu. Procent klucza alokacji towaru jest ignorowana podczas generowania prognoz popytu. Prognozy są tworzone tylko na podstawie danych historycznych. 

Towar i jego wymiary muszą być częścią tylko jednego klucza alokacji produktów, o ile klucz jest używany podczas tworzenia prognozy. 

Aby dodać jednostka składowania zapasu (JSZ) do klucza alokacji towaru, przejdź do **Master planning**&gt;**instalacji**&gt;**Prognozowanie popytu**&gt;**klucze alokacji towaru**. Na stronie **przypisywania towarów** przypisz produkty do klucza alokacji.

## <a name="intercompany-planning-groups"></a>Grupy planowania międzyfirmowego
Prognozowanie popytu generuje prognozy w obrębie firmy. W usłudze Microsoft Dynamics 365 dla operacji firm, które są planowane razem są grupowane w jedną grupa planowania międzyfirmowego. Aby określić dla każdej firmy, której klucze alokacji towaru należy uznać za Prognozowanie popytu, kojarzenie klucza alokacji towaru z międzyfirmowego planowania członka grupy przechodząc do **Master planning**&gt;**instalacji**&gt;**grup planowania międzyfirmowego**. 

Domyślnie jeśli nie klucze alokacji towaru są przypisane do członkowie grupy planowania międzyfirmowego prognozy popytu jest obliczana dla wszystkich elementów, które zostały przypisane do wszystkich kluczy alokacji towaru z wszystkich 365 Dynamics dla firm operacji. Dodatkowe opcje filtrowania dla firm i klucze alokacji produktów są dostępne na stronie **generowania bazowej prognozy statystycznej**. 

Przejrzyj liczbę pozycji podlegających prognozie. Niepotrzebne pozycje mogą powodować zwiększenie kosztów, jeśli korzystasz z usługi uczenia maszynowego Microsoft Azure.

## <a name="demand-forecasting-parameters"></a>Parametry prognozowania popytu
Aby skonfigurować parametry prognozowania popytu, przejdź do **Master planning**&gt;**instalacji**&gt;**prognozowania parametrów popytu**. Prognozowanie popytu jest uruchamiane w obrębie firmy, dlatego to ustawienie ma charakter globalny. Innymi słowy konfiguracja ma zastosowanie do wszystkich firm. 

Prognozowanie popytu generuje prognozy w ilościach. W związku z tym w polu **Jednostka prognozy popytu** należy określić jednostki miary, w których mają być wyrażone ilości. Jednostka miary musi być unikatowa w celu zagwarantowania, że agregacja i rozdział procentowy mają sens. Aby uzyskać więcej informacji o agregacji i rozdziale procentowym, zobacz [Ręczne korekty prognozy bazowej](manual-adjustments-baseline-forecast.md). Dla każdej jednostki miary używanej dla jednostek SKU zawartych w prognozie popytu należy sprawdzić, czy istnieje reguła konwersji dla jednostki miary i ogólna jednostka miary prognozowania. Po uruchomieniu prognozy rejestrowana jest lista towarów, które nie mają konwersji jednostki miary, ułatwiając wprowadzenie korekty w ustawieniach. 

Prognozowanie popytu może służyć do przewidywania zarówno zależnego, jak i niezależnego popytu. Jeśli na przykład zaznaczone jest tylko pole wyboru **Zamówienie sprzedaży** i jeśli wszystkie towary objęte prognozą są towarami, które są sprzedawane, system oblicza popyt niezależny. Można jednak dodawać składniki podrzędne o znaczeniu krytycznym do kluczy alokacji produktów i uwzględniać je w prognozie popytu. W takim przypadku jeśli zaznaczone jest pole wyboru **Wiersz produkcji**, obliczana jest prognoza zależna. 

Istnieją dwie metody tworzenia podstawowej prognozy w usłudze Dynamics 365 dla operacji. Modeli prognozowania można używać w oparciu o dane historyczne lub można te dane historyczne tylko skopiować do prognozy. Pole **Strategia generowania prognozy** pozwala wybrać między tymi dwoma metodami. Aby używać modeli prognozy, zaznacz opcję **Uczenie maszynowe Azure**. 

Klikając **Wymiary prognozy** w lewym okienku na stronie **Parametry prognozowania popytu**, możesz też wybrać zestaw wymiarów prognozy, które mają być używane przy generowaniu prognozy popytu. Wymiar prognozy wskazuje poziom szczegółów, które dla którego prognoza jest definiowana. Firma, oddział i klucz alokacji produktów są obowiązkowe w wymiarach prognozy, ale można również tworzyć prognozy na poziomie magazynu, stanu zapasów, grupy odbiorców, konta odbiorców, kraju/regionu, stanu i towaru oraz wymiaru wszystkich towarów. 

W dowolnym momencie można dodawać wymiary prognozy do listy wymiarów używanych do prognozowania popytu. Można też usunąć z listy wymiary prognozy. Ręczne korekty zostaną jednak utracone po dodaniu lub usunięciu wymiaru prognozy. 

Nie wszystkie towary zachowują się w taki sam sposób z perspektywy prognozowania popytu. Podobne towary mogą być pogrupowane w jeden klucz alokacji produktów i parametry, takie jak typy transakcji i ustawienia metod prognozy można ustawić według klucza alokacji produktów. Kliknij **Klucze alokacji produktów** w lewym okienku na stronie **Parametry prognozowania popytu**. 

Do generowania prognozy, Dynamics 365 dla operacji jest używana usługa sieci web uczenie maszynowe. Aby połączyć się z usługą, należy podać Dynamics 365 dla operacji następujące informacje po zalogowaniu się do programu Microsoft omówienie:

-   Klucz sieciowy API
-   Końcowy URL usługi sieciowej
-   Nazwa konta magazynu systemu Azure
-   Klucz konta magazynu systemu Azure

**Uwaga:** nazwa konta i klucz konta magazynu systemu są wymagane tylko w przypadku używania niestandardowego konta magazynu. W przypadku wdrażania wersji lokalnej, musi mieć konto niestandardowe magazynu Azure, usługa uczenie maszynowe, aby dostęp do danych historycznych. 

Tworzenie prognoz popytu, można wdrożyć własne usługi przy użyciu Studio uczenia maszynowego lub Dynamics 365 dla operacji żądanie prognozowania eksperymentów. Instrukcje dotyczące wdrażania usługi Dynamics 365 dla operacji żądanie prognozowania eksperymentów jako usługi sieci web są dostępne 365 Dynamics dla operacji. Na stronie **Parametry prognozowania popytu** kliknij kartę **Uczenie maszynowe Azure**.

## <a name="settings-for-the-dynamics-365-for-operations-demand-forecasting-machine-learning-service"></a>Ustawienia dla usługi Dynamics 365 dla operacji żądać prognozowania usługa uczenie komputera
Aby wyświetlić parametry, które mogą być skonfigurowane dla usługi Dynamics 365 dla działania wymagają usługi prognozowania, przejdź do **Planowanie główne**&gt;**instalacji**&gt;**Prognozowanie popytu**&gt;**prognozowania parametrów algorytmu**. **Prognozowania parametrów algorytmu** strona zawiera wartości domyślne dla parametrów. Można zastąpić te parametry na **prognozowania parametrów popytu** strony. Na karcie **Ogólne** można zastąpi parametry globalnie lub użyć karty **Klucze alokacji produktów**, aby zastąpić te parametry według klucza alokacji produktów. Parametry, które są zastępowane dla klucza alokacji produktów mają wpływ tylko prognozę towarów, które są skojarzone z tym kluczem alokacji towaru.

<a name="see-also"></a>Informacje dodatkowe
--------

[Introduction to demand forecasting](introduction-demand-forecasting.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)


