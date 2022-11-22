## Functional extensions for consistency with Javascript/Typescript integrations    
    
    public static IEnumerable<TResult> Map<TSource, TResult>
        (this IEnumerable<TSource> source, Func<TSource, TResult> map) => source.Select(map);


    public static IEnumerable<TSource> Filter<TSource>
        (this IEnumerable<TSource> source, Func<TSource, bool> filter) => source.Where(filter);


    public static TResult Reduce<TAccumulator, TSource, TResult>
        (
            this IEnumerable<TSource> source,
            TAccumulator seed,
            Func<TAccumulator, TSource, TAccumulator> reducer,
            Func<TAccumulator, TResult> resultSelector
        ) => source.Aggregate(seed, reducer, resultSelector);
