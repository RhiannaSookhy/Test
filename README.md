# Test
BEE2041
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "ebafda4b",
   "metadata": {},
   "outputs": [],
   "source": [
    "#As later we use large data frames and plots with lots of data points.\n",
    "\n",
    "import warnings\n",
    "\n",
    "# Filter out warnings\n",
    "warnings.filterwarnings(\"ignore\")"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "d98f2e7a",
   "metadata": {},
   "source": [
    "(a) Import each dataset into memory as a separate data frame, keeping all countries as your sample."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "id": "353fabba",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Freedom of Expression Dataset:\n",
      "       country   1975   1976   1977   1978   1979   1980   1981   1982   1983  \\\n",
      "0  Afghanistan  35.80  35.80  35.80  23.10  21.70  21.70  27.50  25.40  27.50   \n",
      "1       Angola  23.30  23.30  23.30  23.30  23.30  23.30  23.20  23.20  23.20   \n",
      "2      Albania   4.28   4.28   4.28   4.28   4.28   4.28   4.24   4.24   4.24   \n",
      "3          UAE  30.30  33.30  35.20  35.20  35.20  33.30  34.00  34.00  34.00   \n",
      "4    Argentina  47.40  27.20  15.30  15.30  15.30  15.30  16.30  19.00  35.60   \n",
      "\n",
      "   ...  2012  2013  2014  2015  2016  2017  2018  2019  2020  2021  \n",
      "0  ...  49.6  49.6  49.6  46.3  44.3  49.0  50.6  44.3  50.6  28.7  \n",
      "1  ...  46.3  46.3  46.3  46.3  46.3  44.3  51.9  51.9  53.1  46.3  \n",
      "2  ...  60.7  57.0  57.0  57.0  57.0  60.7  57.0  57.0  54.8  54.8  \n",
      "3  ...  35.4  35.4  35.4  34.6  33.7  32.8  32.8  32.8  32.8  30.4  \n",
      "4  ...  67.9  69.7  71.3  67.9  72.7  70.3  70.3  71.2  79.5  72.7  \n",
      "\n",
      "[5 rows x 48 columns]\n",
      "\n",
      "Political Stability Dataset:\n",
      "       country  1996  1997  1998  1999  2000  2001  2002  2003  2004  ...  \\\n",
      "0        Aruba   NaN   NaN   NaN   NaN   NaN   NaN   NaN   NaN   1.0  ...   \n",
      "1  Afghanistan   2.0   NaN   2.0   NaN   2.0   NaN   2.0   2.0   4.0  ...   \n",
      "2       Angola   4.0   NaN   4.0   NaN   4.0   NaN   4.0   5.0   6.0  ...   \n",
      "3      Albania   3.0   NaN   3.0   NaN   3.0   NaN   3.0   3.0   4.0  ...   \n",
      "4      Andorra   1.0   NaN   1.0   NaN   1.0   NaN   1.0   2.0   2.0  ...   \n",
      "\n",
      "   2013  2014  2015  2016  2017  2018  2019  2020  2021  2022  \n",
      "0     3     3     3     3     3     3     3     3     3     3  \n",
      "1     6     6     6     6     6     6     6     5     5     5  \n",
      "2     7     7     6     6     7     7     7     6     7     7  \n",
      "3     8     8     8     8     8     8     7     6     6     6  \n",
      "4     2     1     2     2     2     2     3     3     3     3  \n",
      "\n",
      "[5 rows x 28 columns]\n"
     ]
    }
   ],
   "source": [
    "#Part A\n",
    "import pandas as pd\n",
    "\n",
    "# Load the dataset for freedom of expression\n",
    "freedom_of_expression_df = pd.read_csv('fexpression_idea.csv')\n",
    "\n",
    "# Load the dataset for political stability and absence of violence/terrorism\n",
    "political_stability_df = pd.read_csv('pv_no_src.csv')\n",
    "\n",
    "# Display the first few rows of the freedom of expression dataset\n",
    "print(\"Freedom of Expression Dataset:\")\n",
    "print(freedom_of_expression_df.head())\n",
    "\n",
    "# Display the first few rows of the political stability dataset\n",
    "print(\"\\nPolitical Stability Dataset:\")\n",
    "print(political_stability_df.head())"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "5527964c",
   "metadata": {},
   "source": [
    "(b) If data are not already stored in this way, please reshape data so that they consist of a single line\n",
    "of data for each country and year."
   ]
  },
