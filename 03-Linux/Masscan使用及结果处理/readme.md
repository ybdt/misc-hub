用法如下：
```
time=$(date "+%Y_%m_%d_%H_%M_%S")
masscan -p1-65535 --rate=10000 -oL ${time}.txt -iL input.txt --excludefile exclude.txt
```

结果处理：
```
import argparse

def usage():
    parser = argparse.ArgumentParser(description="Example: python3 masscan-Result-Extractor.py -f out.txt");
    parser.add_argument("-f", "--file", help="Masscan扫描以-oL（文本格式）输出的结果", required=True);
    args = parser.parse_args();
    txt_file = args.file.strip("./");
    return txt_file;

def txt_Extractor_and_txt_Writer(txt_file):
    with open(txt_file + "-legal", "w", encoding="UTF-8") as fw:
        with open(txt_file, "r", encoding="UTF-8") as fr:
            lines = fr.readlines();
            for line in lines:
                line_list = line.split();
                if len(line_list) != 5:
                    continue;
                else: 
                    url = "http://{0}:{1}".format(line_list[3], line_list[2]);
                    fw.write(url + "\n")

def main():
    txt_file = usage();
    txt_Extractor_and_txt_Writer(txt_file);

main();
```