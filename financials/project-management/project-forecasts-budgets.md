---
title: "Prognozy i budżety projektów"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ForecastModel, ProjYearEndProcess
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23501
ms.assetid: 4e6d1384-19a2-4232-b3f3-d2590c218bd7
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7d0e9bebe67f6e028faf1237fa4fb392004a1204
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="project-forecasts-and-budgets"></a>Prognozy i budżety projektów

[!include[banner](../includes/banner.md)]




Program Microsoft Dynamics 365 for Operations umożliwia obsługę i kontrolę projektów na dwa sposoby: za pomocą prognoz projektów i budżetów projektów. 

Korzystaj z prognozowania projektu, jeśli Twoja organizacja ma perspektywę organizacyjną i koncentruje się przychodach i kosztach pochodzących z określonych transakcji. Korzystaj z budżetowania projektu, jeśli Twoja organizacja bardziej koncentruje się na kwotach finansowych. 

Zarówno prognozy projektu, jak i prognozy budżetu używają modeli prognoz do wstrzymywania przewidywanych kwot transakcji. 

Każda metoda ma swoje zalety. Przed wybieraniem metody w danej organizacji, należy uwzględnić następujące kwestie.

|                           |                                                                                                                                                                                                                                                         |                                                                                                                                                                         |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           | **Prognozowanie projektu**                                                                                                                                                                                                                                 | **Tworzenie budżetu dla projektu**                                                                                                                                                   |
| **Alokacja okresu**     | Nie można jawnie alokować transakcji w okresie obrachunkowym. Zamiast tego prognoza i kontrola prognozy, są oparte na okresie użytkowania projektu. Ponieważ prognozy są oparte na określonej dacie, należy rozpoznawać okres na podstawie daty. | Nie można jawnie alokować transakcji w całym okresie użytkowania projektu lub całym okresie obrachunkowym. W przypadku alokowania według okresu można przenosić niewykorzystane kwoty do przodu do następnego okresu obrachunkowego. |
| **Wyświetlanie transakcji**  | Transakcje można wyświetlić w formularzu prognozy, gdzie można zobaczyć prognozy dla całej firmy i we wszystkich projektach, niezależnie od hierarchii. Aby wyróżnić dany projekt w widoku, należy zastosować filtr danych.                                       | Możesz przejrzeć transakcje budżetu dla hierarchii jednego projektu. W związku z tym można wyświetlić szczegóły transakcji dla projektu nadrzędnego lub jego podprojektów.                 |
| **Zmienne transakcji** | Po wprowadzeniu transakcji prognozowych można użyć każdego atrybutu, który istnieje dla rzeczywistych transakcji. Umożliwia to uzyskanie dokładniejszych informacji w prognozie. Na przykład można wprowadzić szczegółowe informacje dla pracowników, towarów, ilości lub właściwości wiersza.         | Po wprowadzeniu szczegółów budżetu można użyć kwot, kategorii i działań.                                                                                    |
| **Zabezpieczenia**              | Prognozowanie jest oparte na transakcjach wprowadzonych w formularzach prognozy i wiąże się z mechanizm kontroli procesu. Każdy pracownik, który ma uprawnienia do formularza prognozy, możne wprowadzać zmiany informacji bez zatwierdzenia.                                        | Budżetowanie używa systemu przepływu pracy, który umożliwia zarządzanie zmianami i pozwala zachować historię zmian.                                                       |
| **Typy wpisów**           | Zapisy transakcji prognozy są oparte na liczbie jednostek oraz na koszcie i cenach sprzedaży jednostki.                                                                                                                                                       | Szczegóły budżetu są oparte na kwotach, które są podzielone między koszty i przychody.                                                                                        |
| **Modele prognoz**       | Ponieważ każda prognoza musi być skojarzona z modelem, można utworzyć kilka modeli prognozy oraz skonfigurować podmodele.                                                                                                                               | Budżetowanie projektów ogranicza modele prognozy, które są używane do budżetowania. Mniej modeli prognozy może pomóc zwiększyć spójność w prognozach.                           |
| **Przekroczenia kosztów**         | Można tylko zezwolić lub nie zezwolić na wprowadzanie transakcji powodujących przekroczenie kosztów.                                                                                                                                                                | Tworzenie budżetu projektu oferuje użytkownikom dodatkowe opcje kontroli. Można zezwolić na ostrzeżenia i przekroczenia.                                                                   |
| **Kontrola**               | Kontrola prognozy jest wykonywana przy użyciu redukcji prognozy. Wartości rzeczywiste są odejmowane od salda transakcji prognozy bez żadnych inspekcji. To może utrudniać śledzenie w miejscach, w których dochodzi do rzeczywistych transakcji.                   | W kontroli budżetu projektu rzeczywiste kwoty są odejmowane od kwot pozostałego budżetu. Umożliwia to uzyskanie dokładniejszych danych inspekcji.                                   |

## <a name="project-forecasts"></a>Prognozy projektów
Korzystając z prognozowania projektu, transakcje prognozy można wprowadzać w formularzach prognozy dla każdego typu transakcji. Każdy atrybut, który jest dostępny dla rzeczywistej transakcji, może być użyty dla transakcji prognozy; na przykład rentowność wiersza, atrybuty wiersza, pracownicy i opisy. Można także projektować, po jakim czasie ponosi się koszt zafakturowany na odbiorcę. 

Transakcje prognozowania projektu są oparte na jednostkach i kwotach. 

Należy skojarzyć każdą prognozę projektu z modele prognozy. Po wpisaniu transakcji prognozy model transakcji jest automatycznie sugerowany. Model prognozy pełni rolę kontenera dla transakcji prognozy. 

Można wyznaczyć modele prognozy jako podmodele dla modelu. Pozwala to na tworzenie prognoz według regionu, okresu czasu lub działu. Można skopiować transakcje prognozy w modelu, aby utworzyć nowy model, a także przenieść transakcje do księgi głównej. Ponieważ istnieje relacja jeden do jednego między prognozą i modelem, każdy model prognozy stanowi osobny budżet dla projektu. 

Modele prognozy mogą używać redukcji prognozy jako mechanizmu kontroli dla projektów. Dzięki redukcji prognozy transakcje rzeczywiste ograniczają salda transakcji prognozy. Jednak ponieważ redukcja prognozy jest stosowana do najwyższego projektu w hierarchii, zapewnia ograniczone wyświetlanie zmian w prognozie. Na przykład, jeśli pracownik nie jest skojarzony z podprojektem, rzeczywiste transakcje dla pracownika są księgowane dla projektu nadrzędnego. To może utrudniać śledzenie zmian, ponieważ nie można łatwo określić, która transakcja w którym podprojekcie spowodowała zmniejszenie kwoty prognozy. Z tego powodu warto utworzyć kopię modelu prognozy, która ma być używana w redukcji prognozy. Następnie można używać raportów do wyświetlania, co było pierwotnie prognozowane. 

Można poprawiać, kopiować, usuwać lub przenosić prognozy projektu do budżetu księgi głównej. Nie ma jednak kontroli procesu. Jakikolwiek pracownik z uprawnieniami do formularza prognozy może wprowadzać korekty bez oceny.

-   **Popraw** — W tych samych formularzach, gdzie wprowadzono oryginalne zapisy, można wykonać korekty transakcji prognozy.
-   **Kopiuj lub usuń** — W przypadku kopiowania transakcji prognozy, wiersze transakcji jednego modelu prognozy są kopiowane do innego modelu prognozy. W przypadku usuwania prognozy, transakcje prognozy są usuwane z modelu prognozy. Aby ograniczyć transakcje prognozy, które są kopiowane lub usuwane, zaznacz określone typy transakcji i daty. Umożliwia to skopiowanie lub usunięcie tylko określonych części prognozy.
-   **Przenieś** — W przypadku przenoszenia prognozy projektu do budżetu księgi głównej, przenosisz transakcje prognozy z modelu prognozy do budżetu księgi głównej. Możesz zastąpić wszelkie uprzednio przeniesione transakcje w budżecie księgi głównej, do którego jest przenoszona prognoza projektu.

## <a name="project-budgets"></a>Budżety projektów
Budżet projektu jest prostszą metodą niż prognozowanie, mimo że integruje się z modelami prognozy. Używa formularza jednorazowego wpisu dla szczegółów oryginalnego budżetu i korekt, i pozwala opierać prognozy tylko na kwocie, kategorii i działaniu. 

W budżetowaniu projektu wszystkie oryginalne budżety i korekty muszą zostać wysłane do przepływu pracy projektu do zatwierdzenia. Przepływy pracy dają większą kontrolę nad procesem i tworzą rekord historii zmian. 

Budżetowanie projektów przypomina budżetowanie księgi głównej, ale jest szybsze i łatwiejsze do konfigurowania. Wiele opcji w budżetowaniu księgi głównej, np. sekwencja identyfikatorów lub waluta, nie wymagają oddzielnej konfiguracji dla projektów.

Budżety projektów są automatycznie kojarzone z dwoma modelami prognozy, jednym dla budżetu oryginalnej i jednym dla pozostałego budżetu. Z tego względu raporty oparte na modelach prognozy mogą używać danych budżetu. Po przypisaniu budżetu projektu system tworzy transakcje prognozy w oparciu o skojarzone modele, które są używane do celów raportowania i kontroli.

## <a name="forecast-models"></a>Modele prognoz
Modele prognozy mają hierarchię jednowarstwową. To znaczy, że jedna prognoza projektu musi być skojarzona z jednym modelem prognozy.

Jeśli używasz prognozowania projektu, modele można określić jako podmodele Następnie można tworzyć prognozy według okresu, działu lub regionu. Na przykład można utworzyć model prognozy na rok, a następnie utworzyć podmodele prognoz regionalnych Północny Wschód, Południowy Wschód, Północny Zachód i Południowy Zachód dla, które przesyłają szefowie regionów. Wybierając różne opcje w dostępnych raportach, można wyświetlać informacje według całkowitej prognozy lub podmodelu.




