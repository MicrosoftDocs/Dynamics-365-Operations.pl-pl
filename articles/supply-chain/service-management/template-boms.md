---
title: Szablony BOM
description: Szablon listy składowej (BOM) zawiera standardową listę składników przedmiotów serwisu, które są regularnie serwisowane.
author: ShylaThompson
manager: tfehr
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8842a293a50efb24590784cc52ef0254eca10e3a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206549"
---
# <a name="template-boms"></a>Szablony BOM    

[!include [banner](../includes/banner.md)]


Szablon listy składowej (BOM) prezentuje standardową listę składników przedmiotów serwisu, które są regularnie serwisowane. Składniki wymienione w szablonie BOM są niezależnymi podskładnikami przedmiotu serwisu. Gdy szablon BOM zostanie zastosowany do przedmiotu serwisu, można zachować spis podksładników, które zostały wymienione w przedmiocie serwisu.

Aby zastosować szablon BOM do umowy serwisowej lub zlecenia serwisowego, należy go dołączyć do relacji przedmiotu serwisu.


> [!NOTE]
> <P>Do jednego przedmiotu serwisu można zastosować tylko jeden szablon BOM.</P>

## <a name="create-a-template-bom"></a>Tworzenie szablonu BOM

Poniższa tabela zawiera informacje o różnych metodach tworzenia szablonów BOM.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Metoda</p></th>
<th><p>opis</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Produkcja</p></td>
<td><p>Szablon BOM bazuje na zleceniu produkcyjnym. Ta opcja jest odpowiednia tylko wtedy, gdy działasz w środowisku produkcyjnym. Zaleta jest taka, że masz aktualną, szczegółową listę składników tworzących towar.</p></td>
</tr>
<tr class="even">
<td><p>Towar BOM</p></td>
<td><p>Szablon BOM bazuje na BOM towaru. BOM towaru, w przeciwieństwie do BOM produkcji, jest statyczną listą składników tworzących towar.</p></td>
</tr>
<tr class="odd">
<td><p>Istniejący szablon</p></td>
<td><p>Szablon bazuje na istniejącym szablonie BOM.</p></td>
</tr>
<tr class="even">
<td><p>Ręczny</p></td>
<td><p>Jeśli wiadomo, jakie części są zazwyczaj wymieniane w przedmiocie serwisu, można ręcznie utworzyć szablon BOM. Ta metoda pomaga uzyskać pewność, że składniki umieszczone w szablonie odzwierciedlają faktyczne potrzeby miejsca pracy.</p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a>Stosowanie szablonu BOM do umowy serwisowej lub zlecenia serwisowego

Szablon BOM można zastosować do umowy serwisowej i/lub zlecenia serwisowego. Umowa serwisowa zazwyczaj dotyczy długoterminowej relacji z odbiorcą. Historia wymiany zarejestrowana w BOM serwisu zawiera dane, które są przydatne w umowie serwisowej.

Można również zastosować szablon BOM do zlecenia serwisowego w celu rejestrowania historii czynności serwisowych wykonywanych na przedmiocie serwisu.

## <a name="copy-the-history-of-a-service-bom"></a>Kopiowanie historii BOM serwisu

Historię wiersza BOM serwisu można kopiować między umowami serwisowymi. Skopiowanie historii serwisu między umowami pomaga zachować rejestr wymiany części.

**Przykład**

Powstała trzyletnia umowa serwisowa dotycząca serwisowania samochodu klienta. W tym okresie odbiorca przyzwyczaił się do dobrej opieki serwisowej oferowanej przez firmę. Z tego względu po wygaśnięciu umowy chce zawrzeć nową. Teraz można wynegocjować dla firmy lepsze warunki. Ponieważ rejestr wymienionych części może przydać się w przyszłości, kopiujesz historię BOM serwisu do nowej umowy.

## <a name="modify-the-template-bom"></a>Modyfikowanie szablonu BOM

Jeśli szablon BOM nie został dołączony do przedmiotu serwisu, można w nim modyfikować i usuwać wiersze. Jeśli szablon BOM został dołączony do przedmiotu serwisu, można modyfikować tylko lokalną wersję BOM. Aby skopiować konfigurację wersji lokalnej szablonu BOM, można utworzyć nowy szablon BOM oparty na wersji lokalnej. Aby uzyskać więcej informacji, zobacz [Modyfikowanie BOM serwisu](modify-service-bom.md).

Zastąpienie towaru w BOM można zarejestrować w wierszu BOM w konstruktorze BOM. Opcjonalnie dla przedmiotu wymiany można utworzyć wiersz zlecenia serwisowego. Jeśli utworzysz wiersz zlecenia serwisowego, można wystawić fakturę za część zamienną. Jeśli wiersz zlecenia serwisowego dotyczący wymiany nie zostanie utworzony, informacja o wymianie pozostanie zarejestrowana na potrzeby historii przedmiotu serwisu.

## <a name="change-how-information-on-the-bom-line-is-displayed"></a>Zmiana sposobu wyświetlania informacji w wierszu BOM

Sposób wyświetlania informacji w wierszu BOM można zmieniać we wszystkich szablonach BOM oraz w BOM serwisu. Zmiany zostaną zastosowane do wszystkich szablonów BOM i BOM serwisu. Dotyczy to również tych, które są dołączone do przedmiotów serwisu.

## <a name="set-up-number-sequences-for-template-boms"></a>Konfigurowanie numeracji szablonów BOM

Aby korzystać z szablonów BOM, należy skonfigurować dwie numeracje. Jedna z nich musi dotyczyć szablonu BOM, a druga numeru wiersza historii BOM.


> [!NOTE]
> <P>Numeracje są używane do przydzielania identyfikatorów rekordom, które tego wymagają. Zanim będzie można przypisać numerację do szablonu BOM lub numer wiersza historii BOM, należy skonfigurować kody numeracji.</P>


## <a name="set-up-number-sequences"></a>Ustawienie sekwencji numerów

1.  Na stronie listy **Sekwencje numerów** utwórz numerację dla szablonów BOM i numeru wiersza historii BOM. 

2.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Parametry modułu Zarządzanie serwisem**.

3.  Kliknij przycisk **Sekwencje numerów**, a następnie wybierz kod numeracji dla odwołań do numeracji utworzonych w formularza **Sekwencje numerów**.

4.  Zamknij formularz, aby zapisać zmiany.


> [!NOTE]
> <P>Numer wiersza historii BOM jest używany przez system do skojarzenia transakcji w historii BOM z umową serwisową lub zleceniem serwisowym. Numer nie jest wyświetlany w interfejsie użytkownika.</P>



## <a name="see-also"></a>Informacje dodatkowe

[Tworzenie szablonu BOM](create-template-bom.md)

[Zarządzanie szablonami BOM w relacjach przedmiotów](manage-template-boms-on-object-relations.md)

[Modyfikowanie BOM serwisu](modify-service-bom.md)

 


