<<code "DataSet.Append;
Dataset.FieldByName('Campo1').AsInteger := 10;
Dataset.FieldByName('Campo2').AsString := 'Débito';
Dataset.FieldByName('Campo3').AsFloat := 150.00;
DataSet.Post;">>

O código não está incorreto, mas pode ser melhorado! Com um método (pouco conhecido) chamado AppendRecord, pode-se reduzir essas cinco linhas em apenas uma:

<<code "DataSet.AppendRecord([10, 'Débito', 150.00]);">>

---

[Dicas Clean Code](https://www.andrecelestino.com/delphi-breves-dicas-de-clean-code/)
