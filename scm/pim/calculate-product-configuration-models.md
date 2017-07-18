---
title: "Obliczenia dla modeli produktu w konfiguracji — często zadawane pytania"
description: "W tym artykule opisano obliczenia dla modeli konfiguracji produktu i wyjaśniono sposób korzystania z obliczeń wraz z ograniczeniami."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f13d03e5d1a26a5c87d71732b692537be94bdfb8
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="calculations-for-product-configuration-models-faq"></a>Obliczenia dla modeli produktu w konfiguracji — często zadawane pytania

[!include[banner](../includes/banner.md)]


W tym artykule opisano obliczenia dla modeli konfiguracji produktu i wyjaśniono sposób korzystania z obliczeń wraz z ograniczeniami.

Obliczenia mogą służyć do operacji arytmetycznych lub logicznych. Uzupełniają one ograniczenia wyrażenia w modelach konfiguracji produktu. Można zdefiniować obliczenia na stronie **Szczegóły modelu konfiguracji produktu**, a następnie utworzyć wyrażenia w obliczeniach w edytorze wyrażenia. Aby uzyskać więcej informacji, zobacz Utwórz obliczenia.

## <a name="what-is-a-calculation"></a>Czym jest obliczenie?
Obliczenie jest elementem używanym w modelu konfiguracji produktu. Obliczenia uzupełniają ograniczenia, umożliwiając obliczanie wartości przy użyciu liczb dziesiętnych podczas konfigurowania produktu. Ponadto obliczenia mają większy zestaw dostępnych operatorów niż ograniczenia.  

Podobnie jak ograniczenie, obliczenie jest skojarzone z określonym składnikiem modelu konfiguracji produktu i nie może być ponownie używane lub współużytkowane z innym składnikiem. Istotna różnica pomiędzy obliczeniami i ograniczeniami polega na tym, że obliczenia są konieczne (jednokierunkowe), a ograniczenia deklaratywne (dwukierunkowe). Aby uzyskać więcej informacji o ograniczeniach, zobacz [Ograniczenie wyrażenia i powiązane tabele](expression-constraints-table-constraints-product-configuration-models.md).  

Obliczenia składają się z atrybutu docelowego oraz wyrażenia obliczenia.

## <a name="what-is-a-target-attribute"></a>Czym jest atrybut docelowy?
Atrybut docelowy jest atrybutem, który odbiera wynik obliczeń w wyrażeniu.  

W poniższym wyrażeniu, atrybut docelowy to miara obrusu:  

**Wyrażenie:** If\[decimalAttribute1 &lt;= decimalAttribute2, Prawa, Fałsz\]  

**DecimalAttribute1** to długość stołu, a **decimalAttribute2** to długości obrusu. To wyrażenie zwróci wartość **Prawda** (True) do atrybutu docelowego, jeśli **dziesiętny atrybut 2** (decimalAttribute2) jest większy niż lub równy **dziesiętnemu atrybutowi 1** (decimalAttribute1). W przeciwnym wypadku wyrażenie zwróci wartość **Fałsz** (False). Sposób pomiaru obrusu jest dopuszczalny, jeśli długość obrusu jest równa lub przekracza długość stołu.

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>Jakie typy atrybutów można ustawić jako atrybuty docelowe?
Wszystkie typy atrybutów, które są obsługiwane w przypadku konfiguratora produktów, można ustawić jako atrybuty docelowe, z wyjątkiem tekstu bez stałej listy.

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>Czy wartość dla atrybutu docelowego może ograniczyć wartości wejściowe atrybutów w obliczeniach?
Nie, wartość dla atrybutu docelowego nie może ograniczyć wartości wejściowe atrybutów w obliczeniach, ponieważ obliczenia są jednokierunkowe. Z tego względu wartość atrybutu docelowego jest ustawiona na podstawie zmian wartości wejściowych atrybutów, ale zmiana wartości docelowej nie ma wpływu na wartości wejściowych atrybutów. To zachowanie różni się od zachowania ograniczeń. Ograniczenia mogą występować w obu kierunkach.

### <a name="example"></a>Przykład

W poniższym wyrażeniu celem obliczenia jest długość kabla zasilającego, a wartością wejściową jest kolor.  

**Wyrażenie:** \[If Kolor == "Zielony", 1,5, 1,0\]  

Podczas konfigurowania towaru obliczenie generuje **1,5** jako długość kabla zasilającego, jeśli **Zielony** zostanie określony jako wartość atrybutu koloru. Jeśli określisz jakikolwiek inny kolor, długość będzie ustawiona jako **1.0**. Jednak ponieważ obliczenia są jednokierunkowe, obliczenie nie ustawia wartości atrybutu koloru na **zielony** w przypadku określenia długości na **1,5**.

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>Co się stanie, jeśli obliczenie ma atrybut docelowy typu liczby całkowitej, ale wynik obliczenia to liczba dziesiętna?
Jeśli atrybut docelowy jest typu liczba całkowita, ale obliczenie wygeneruje liczbę dziesiętną, zostanie zwrócona tylko część całkowita obliczonego wyniku. Części dziesiętne są usuwane, a wynik nie jest zaokrąglany. Na przykład wynik równy 12.70 jest wyświetlany jako 12.

## <a name="when-do-calculations-occur"></a>Kiedy mają miejsce obliczenia?
Obliczenia są wykonywane po dostarczeniu wartości dla wszystkich atrybutów wejściowych.

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>Czy można zastąpić wartość, która jest obliczana dla atrybutu docelowego?
Można zastąpić wartość, która jest obliczana dla atrybutu docelowego, o ile dla atrybutu docelowego nie wybrano ustawienia ukryty lub tylko do odczytu.

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-readonly"></a>Jak ustawić atrybut docelowy jako ukryty lub tylko do odczytu?
Aby ustawić atrybut jako ukryty lub tylko do odczytu, należy wykonać następujące czynności:

1.  Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Wspólne** &gt; **Modele konfiguracji produktu**.
2.  Wybierz model konfiguracji produktu, a następnie w okienku akcji, kliknij przycisk **Edytuj**.
3.  Na stronie **Szczegóły modelu konfiguracji produktu opartej na ograniczeniu** wybierz atrybut, który będzie używany jako docelowy.
4.  Na skróconej karcie **Atrybuty** wybierz **Ukryty** lub **Tylko do odczytu**.

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>Czy obliczenie może zastąpić ustawione wartości?
Nr Wartości, które można ustawić podczas konfigurowania produktu, to wartości, które są używane. Obliczenia, który występują, gdy są zmieniane wartości wejściowe w obliczeniach, nie mogą zastąpić wartości ustawionych dla konkretnego atrybutu.

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>Co się dzieje w przypadku usunięcia wartości wejściowej przy obliczaniu?
Jeśli usuniesz przy obliczaniu wartość wejściową, wartość atrybutu docelowego również zostanie usunięta.

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>Dlaczego pojawia się komunikat o błędzie z informacją, że mój model zawiera sprzeczność?
Ten komunikat jest wyświetlany, gdy obliczenie zawiera błąd lub istnieje sprzeczność w jednym lub wielu ograniczeniach. Aby uzyskać więcej informacji dotyczących sprzeczności w ograniczeniach, zobacz temat [Ograniczenie wyrażenia i powiązane tabele](expression-constraints-table-constraints-product-configuration-models.md). Poniżej przedstawiono niektóre sytuacje, w których mogą wystąpić błędy w obliczeniach:

-   Wartość jest dzielona przez zero.
-   Istnieje konflikt między tymi dwoma elementami:
    -   Wartości, które są dostępne dla atrybutu i które są ograniczane przez ograniczenie.
    -   Wartość, która jest generowana za pomocą obliczeń.
-   Wartości, które są zwracane przez obliczenia są poza domeną atrybutu. Przykładem jest liczba całkowita z przedziału \[1..10\], która jest obliczana na 0.

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>Dlaczego pojawia się błąd, nawet jeśli pomyślnie zweryfikowano dany model produktu?
Sprawdzanie poprawności nie zawiera obliczeń. Należy przetestować model konfiguracji produktu w celu znalezienia błędów w obliczeniach. Poniższe kroki zawierają informacje dotyczące sposobu testowania modelu konfiguracji produktu:

1.  Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Wspólne** &gt; **Modele konfiguracji produktu**.
2.  Wybierz model konfiguracji produktu, a następnie w okienku akcji, w grupie **Uruchom** kliknij **Test**.





