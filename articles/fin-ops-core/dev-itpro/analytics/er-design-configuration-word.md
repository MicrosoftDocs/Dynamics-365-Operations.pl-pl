---
title: Projektowanie nowej konfiguracji ER w celu generowania raportów w formacie programu Word
description: W tym temacie wyjaśniono, jak użytkownicy mogą skonfigurować nowy format raportowania elektronicznego (ER), aby generować raporty jako dokumenty programu Microsoft Word.
author: NickSelin
ms.date: 12/17/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 4885caf017fa0f9d36d293fa32aad53c21d3f162
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753583"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a>Projektowanie nowej konfiguracji ER w celu generowania raportów w formacie programu Word

[!include [banner](../includes/banner.md)]

Aby generować raporty jako dokumenty programu Microsoft Word, należy zaprojektować szablon dla tych raportów, korzystając na przykład z aplikacji klasycznej Word. Na poniższej ilustracji przedstawiono przykładowy szablon raportu kontroli, który można wygenerować w celu pokazania szczegółów przetworzonych płatności dostawców.

![Przykładowy szablon raportu kontroli w aplikacji klasycznej Word](./media/er-design-configuration-word-image1.png)

Aby użyć dokumentu programu Word jako szablonu raportów w formacie programu Word, można skonfigurować nowe [rozwiązanie](er-quick-start1-new-solution.md) do [raportowania elektronicznego (ER)](general-electronic-reporting.md). To rozwiązanie musi zawierać [konfigurację](general-electronic-reporting.md#Configuration) zawierającą składnik [formatu](general-electronic-reporting.md#FormatComponentOutbound) ER.

> [!NOTE]
> Podczas tworzenia nowej konfiguracji formatu ER w celu wygenerowania raportów w formacie programu Word należy wybrać program **Word** jako typ formatu w oknie rozwijanym **Utwórz konfigurację** lub pozostawić pole **Typ formatu** puste.

![Tworzenie konfiguracji formatu na stronie Konfiguracje](./media/er-design-configuration-word-image2.gif)

Składnik formatu ER rozwiązania musi zawierać element formatu **Excel\\Plik**, a ten element formatu musi być połączony z dokumentem programu Word, który będzie używany jako szablon do generowania raportów w czasie wykonywania. Aby skonfigurować składnik formatu ER, należy otworzyć [wersję roboczą](general-electronic-reporting.md#component-versioning) utworzonej konfiguracji ER w projektancie formatów ER. Następnie dodaj element **Excel\\Plik**, dołącz szablon programu Word do edytowalnego formatu ER i połącz ten szablon z dodanym elementem **Excel\\Plik**.

> [!NOTE]
> Podczas ręcznego dołączania szablonu należy użyć [typu dokumentu](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types), który został poprzednio [skonfigurowany](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) w obszarze parametrów ER w celu przechowywania szablonów formatów ER.

![Dołączanie szablonu na stronie Projektant formatów](./media/er-design-configuration-word-image3.gif)

Możesz dodać zagnieżdżone elementy **Excel\\Zakres** i **Excel\\Komórka** dla elementu **Excel\\Plik** w celu określenia struktury danych, które będą wprowadzane w raportach generowanych w czasie wykonywania. Następnie należy powiązać te elementy ze źródłami danych formatu edytowalnego raportu ER, aby określić rzeczywiste dane, które będą wprowadzane w raportach generowanych w czasie wykonywania.

![Dodawanie zagnieżdżonych elementów na stronie Projektant formatów](./media/er-design-configuration-word-image4.gif)

Podczas zapisywania zmian w formacie ER w czasie projektowania hierarchiczna struktura formatu jest przechowywana w dołączonym szablonie programu Word jako [niestandardowa część XML](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) o nazwie **Raport**. Musisz uzyskać dostęp do zmodyfikowanego szablonu, pobrać go z aplikacji Finance, zapisać lokalnie i otworzyć w aplikacji klasycznej Word. Na poniższej ilustracji przedstawiono lokalnie przechowywany szablon przykładowy dla raportu kontrolnego zawierającego niestandardową część XML o nazwie **Raport**.

![Wyświetlanie przykładowego szablonu raportu w aplikacji klasycznej Word](./media/er-design-configuration-word-image5.gif)

Gdy powiązania elementów formatu **Excel\\Zakres** i **Excel\\Komórka** są uruchamiane w czasie wykonywania, dane, które każde powiązanie dostarcza, jest umieszczane w wygenerowanym dokumencie programu Word jako indywidualne pole niestandardowej części XML **Raport**. Aby wprowadzić wartości z pól niestandardowej części XML w generowanym dokumencie, musisz dodać odpowiednie [kontrolki zawartości](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) programu Word do szablonu programu Word, aby służyły jako symbole zastępcze dla danych, które będą wypełniane w czasie wykonywania. Aby określić sposób wypełnienia kontrolek zawartości, zamapuj każdą kontrolkę zawartości do odpowiedniego pola niestandardowej części XML **Raport**.

![Dodawanie i mapowanie kontrolek zawartości w aplikacji klasycznej Word](./media/er-design-configuration-word-image6.gif)

Następnie należy zastąpić oryginalny szablon programu Word edytowalnym formatem raportu ER ze zmodyfikowanym szablonem, który teraz zawiera kontrolki zawartości programu Word zamapowane na pola niestandardowej części XML **Raport**.

![Zastępowanie szablonu na stronie Projektant formatów](./media/er-design-configuration-word-image7.gif)

Po uruchomieniu skonfigurowanego formatu ER dołączony szablon programu Word jest używany do generowania nowego raportu. Rzeczywiste dane są przechowywane w raporcie programu Word jako niestandardowa część XML o nazwie **Raport**. Po otwarciu wygenerowanego raportu kontrolki zawartości programu Word są wypełniane danymi z niestandardowej części XML **Raport**.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

**Pytanie:** Skonfigurowano format ER do drukowania dokumentu programu Word zawierającego adres firmy. W szablonie programu Word dla tego formatu ER wstawiono kontrolkę zawartości sformatowaną w celu przedstawienia adresu firmy. W aplikacji Finance wprowadzono adres firmy jako tekst w wielu wierszach i wybrano klawisz **Enter**, aby dodać powrót karetki do każdego wprowadzonego wiersza. Dlatego oczekuję, że adres firmy będzie się pojawiał w generowanych dokumentach jako tekst w wielu wierszach. Adres pojawia się jednak w jednym wierszu tekstu, który zawiera symbole specjalne, a nie powroty karetki. Co jest nie tak z moimi ustawieniami?

**Odpowiedź:** Zamiast korzystania z kontrolki zawartości sformatowanej należy użyć kontrolki zawartości w postaci zwykłego tekstu i zaznaczyć pole wyboru **Zezwalaj na powroty karetki (wiele akapitów)** we właściwościach kontrolki.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Ponowne używanie konfiguracji ER z szablonami programu Excel do generowania raportów w formacie programu Word](./tasks/er-design-configuration-word-2016-11.md)
- [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]